# I_StoreSymAuthKey

- ea: `0x180024378`
- end: `0x180024aa4`
- name: `I_StoreSymAuthKey`
- size: `1836`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800225a0`
- `0x180024f14`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x18000653c`
- `0x1800068bc`
- `0x1800068dc`
- `0x180007988`
- `0x18000a110`
- `0x18000bc48`
- `0x18000bf8c`
- `0x18000c010`
- `0x18000c198`
- `0x18000fafc`
- `0x180010b0c`
- `0x18001130c`
- `0x180019cb4`
- `0x18001a19c`
- `0x18001cd14`
- `0x18001d954`
- `0x18001d9c4`
- `0x18001e8f0`
- `0x180020040`
- `0x18002356c`
- `0x180024378`
- `0x180028250`
- `0x180028494`
- `0x18002bb98`
- `0x1800348a0`
- `0x180037010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800247a1`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800247a1`

## string_xrefs

- `0x180024922`: `Unable to update key map record`
- `0x180024838`: `Unable to create protection key within retry limist`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall I_StoreSymAuthKey(_QWORD *a1, unsigned __int8 a2, char a3, __int64 a4, __int64 *a5)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  int v12; // edx
  const char *v13; // rax
  unsigned int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  _QWORD *v18; // rcx
  int v19; // edx
  const char *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned int v24; // edi
  __int64 v25; // rcx
  unsigned int i; // esi
  __int64 v27; // rcx
  __int64 v28; // rcx
  _QWORD *v29; // rcx
  int v30; // edx
  const char *v31; // rax
  __int64 v32; // rcx
  _QWORD *v33; // rcx
  int v34; // edx
  const char *v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 *v38; // rcx
  __int64 v39; // rdx
  unsigned int SymBlockSize; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v42; // [rsp+38h] [rbp-C8h] BYREF
  char v43; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v45; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v46; // [rsp+58h] [rbp-A8h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+60h] [rbp-A0h] BYREF
  UCHAR pbOutput[4]; // [rsp+68h] [rbp-98h] BYREF
  int v49; // [rsp+6Ch] [rbp-94h] BYREF
  void *v50; // [rsp+70h] [rbp-90h] BYREF
  __int16 v51; // [rsp+78h] [rbp-88h]
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  __int64 v53; // [rsp+88h] [rbp-78h]
  _QWORD v54[3]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v55[3]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v56[3]; // [rsp+C8h] [rbp-38h] BYREF
  NCRYPT_KEY_HANDLE *p_hKey; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v58[3]; // [rsp+E8h] [rbp-18h] BYREF
  __int16 v59; // [rsp+100h] [rbp+0h]
  _QWORD v60[3]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v61[6]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v62[40]; // [rsp+150h] [rbp+50h] BYREF
  int v63; // [rsp+1A0h] [rbp+A0h]
  unsigned __int16 v64[48]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v65[24]; // [rsp+210h] [rbp+110h] BYREF

  v46 = a1;
  v42 = a2;
  v43 = a3;
  v61[5] = a5;
  SymBlockSize = 0;
  v49 = 0;
  strcpy(v65, "I_StoreSymAuthKey");
  v60[0] = v65;
  v60[1] = &v49;
  v60[2] = &SymBlockSize;
  lambda_59147f3b9f10595d3915fe577244bcf4_::operator()(v60);
  v49 = 1;
  v45 = v60;
  v7 = (__int64)v46;
  if ( !v46 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(0, v6);
    v7 = (__int64)v46;
  }
  if ( !(unsigned int)I_IsRoleAuthenticated(v7, 3) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( (unsigned __int8)(v42 + 0x80) > 0x20u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  LOBYTE(v8) = v43;
  if ( (unsigned __int8)((v43 & 0xF) - 2) > 3u )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
    LOBYTE(v8) = v43;
  }
  hObject = 0;
  SymBlockSize = I_LoadSymKeyFromBuffer(*v46, v8, a4, &hObject);
  if ( SymBlockSize )
  {
    WppTraceIndent(v10, 2u);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_15;
    }
    v12 = 88;
    v13 = "Unable to load the symmetric auth key";
LABEL_14:
    WPP_SF_sDs(
      v11[2],
      v12,
      (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
      (_DWORD)WPP_pszIndent,
      SymBlockSize,
      (__int64)v13);
LABEL_15:
    v14 = SymBlockSize;
    goto LABEL_86;
  }
  *(_DWORD *)pbOutput = 0;
  SymBlockSize = I_GetSymBlockSize(hObject, pbOutput);
  if ( SymBlockSize )
  {
    WppTraceIndent(v16, 2u);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_15;
    }
    v12 = 89;
    v13 = "Unable to get auth algorithm block size";
    goto LABEL_14;
  }
  if ( !*(_DWORD *)pbOutput )
    MicrosoftTelemetryAssertTriggeredNoArgs(v16, v15);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v52);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v54);
  SymBlockSize = I_GenerateRandomData(*v46, *(unsigned int *)pbOutput, &v52);
  if ( !SymBlockSize )
  {
    SymBlockSize = I_EncryptSym(hObject);
    if ( SymBlockSize )
    {
      WppTraceIndent(v22, 2u);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      v19 = 91;
      v20 = "Unable to calculate response";
      goto LABEL_28;
    }
    if ( v53 - v52 != v54[1] - v54[0] )
      MicrosoftTelemetryAssertTriggeredNoArgs(v53 - v52, v21);
    memset_0(v64, 0, 0x54u);
    I_KeyMapGetRecord((const struct VCARD_DATA *)*v46, v42, (struct KEY_MAP_RECORD *)v64);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v55);
    if ( v46[19] == v46[20] )
    {
      v24 = SymBlockSize;
    }
    else
    {
      v24 = I_UnprotectMemory(v46 + 19, v55);
      SymBlockSize = v24;
      if ( v24 )
      {
        WppTraceIndent(v23, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sDs(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            92,
            (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
            (_DWORD)WPP_pszIndent,
            SymBlockSize,
            (__int64)"Unable to recover auth key");
        }
        v14 = SymBlockSize;
LABEL_84:
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v55);
        goto LABEL_85;
      }
    }
    memset_0(v62, 0, sizeof(v62));
    v63 = 3;
    hKey = 0;
    for ( i = 0; i < 0xA; ++i )
    {
      SymBlockSize = I_GenerateGuid(v62);
      if ( SymBlockSize )
      {
        WppTraceIndent(v27, 2u);
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v30 = 93;
          v31 = "Unable to generate protection key name";
          goto LABEL_56;
        }
        goto LABEL_57;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      p_hKey = &hKey;
      v50 = v62;
      v28 = a5[7];
      if ( !v28 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      v24 = (*(__int64 (__fastcall **)(__int64, void **, NCRYPT_KEY_HANDLE **, _QWORD *))(*(_QWORD *)v28 + 16LL))(
              v28,
              &v50,
              &p_hKey,
              v54);
      SymBlockSize = v24;
      if ( v24 != -2146893809 )
        break;
    }
    if ( v24 )
    {
      WppTraceIndent(v25, 2u);
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = 94;
        v31 = "Unable to create protection key within retry limist";
LABEL_56:
        WPP_SF_sDs(
          v29[2],
          v30,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          (_DWORD)WPP_pszIndent,
          SymBlockSize,
          (__int64)v31);
      }
LABEL_57:
      v14 = SymBlockSize;
      goto LABEL_83;
    }
    v50 = &hKey;
    v51 = 258;
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v56);
    SymBlockSize = I_KeyMapPackSymAuthKeyBlob(hKey);
    if ( SymBlockSize )
    {
      WppTraceIndent(v32, 2u);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_69;
      }
      v34 = 95;
      v35 = "Unable to pack keys";
    }
    else
    {
      SymBlockSize = I_KeyMapSetRecord((const struct VCARD_DATA *)*v46, v42, (const struct KEY_MAP_RECORD *)v62);
      if ( !SymBlockSize )
      {
        v58[0] = &v46;
        v58[1] = &v42;
        v58[2] = v64;
        v59 = 258;
        v61[0] = &v46;
        v61[1] = &v42;
        v61[2] = &v43;
        v61[3] = &v52;
        v61[4] = v56;
        SymBlockSize = lambda_598cbb1c53868393d2c6419d8abc193c_::operator()(v61);
        if ( SymBlockSize )
        {
          WppTraceIndent(v37, 2u);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_sDs(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              100,
              (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
              (_DWORD)WPP_pszIndent,
              SymBlockSize,
              (__int64)"Updating key maps failed");
          }
        }
        else
        {
          HIBYTE(v51) = 0;
          HIBYTE(v59) = 0;
          I_DeleteKeyMaterial((struct VCARD_DATA *)*v46, (const struct KEY_MAP_RECORD *)v64);
        }
        v14 = SymBlockSize;
        wil::details::ScopeExitFnGuard__lambda_ca4cb570e2f7d20a87829b93eb832cd9___::operator()(v58);
LABEL_82:
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v56);
        wil::details::ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f___::operator()((__int64)&v50);
LABEL_83:
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
        goto LABEL_84;
      }
      WppTraceIndent(v36, 2u);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_69:
        v14 = SymBlockSize;
        goto LABEL_82;
      }
      v34 = 96;
      v35 = "Unable to update key map record";
    }
    WPP_SF_sDs(
      v33[2],
      v34,
      (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
      (_DWORD)WPP_pszIndent,
      SymBlockSize,
      (__int64)v35);
    goto LABEL_69;
  }
  WppTraceIndent(v17, 2u);
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_29;
  }
  v19 = 90;
  v20 = "Unable to generate the challenge";
LABEL_28:
  WPP_SF_sDs(
    v18[2],
    v19,
    (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
    (_DWORD)WPP_pszIndent,
    SymBlockSize,
    (__int64)v20);
LABEL_29:
  v14 = SymBlockSize;
LABEL_85:
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v54);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v52);
LABEL_86:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
  WppTraceUnwinder__lambda_59147f3b9f10595d3915fe577244bcf4____::_WppTraceUnwinder__lambda_59147f3b9f10595d3915fe577244bcf4____(&v45);
  v38 = (__int64 *)a5[7];
  if ( v38 )
  {
    v39 = *v38;
    LOBYTE(v39) = v38 != a5;
    (*(void (__fastcall **)(__int64 *, __int64))(*v38 + 32))(v38, v39);
    a5[7] = 0;
  }
  return v14;
}

```

## disassembly

```asm
0x180024378  push    rbp
0x18002437a  push    rbx
0x18002437b  push    rsi
0x18002437c  push    rdi
0x18002437d  push    r12
0x18002437f  push    r14
0x180024381  push    r15
0x180024383  lea     rbp, [rsp-130h]
0x18002438b  sub     rsp, 230h
0x180024392  mov     rax, cs:__security_cookie
0x180024399  xor     rax, rsp
0x18002439c  mov     [rbp+160h+var_38], rax
0x1800243a3  mov     r14, r9
0x1800243a6  mov     [rsp+260h+var_208], rcx
0x1800243ab  mov     [rsp+260h+var_228], dl
0x1800243af  mov     [rsp+260h+var_220], r8b
0x1800243b4  mov     rbx, [rbp+160h+arg_20]
0x1800243bb  mov     [rbp+160h+var_118], rbx
0x1800243bf  xor     r15d, r15d
0x1800243c2  mov     [rsp+260h+var_230], r15d
0x1800243c7  mov     [rsp+260h+var_1F4], r15d
0x1800243cc  movups  xmm0, xmmword ptr cs:aIStoresymauthk; "I_StoreSymAuthKey"
0x1800243d3  movups  xmmword ptr [rbp+160h+var_50], xmm0
0x1800243da  movzx   eax, word ptr cs:aIStoresymauthk+10h; "y"
0x1800243e1  mov     word ptr [rbp+160h+var_50+10h], ax
0x1800243e8  lea     rax, [rbp+160h+var_50]
0x1800243ef  mov     [rbp+160h+var_158], rax
0x1800243f3  lea     rax, [rsp+260h+var_1F4]
0x1800243f8  mov     [rbp+160h+var_150], rax
0x1800243fc  lea     rax, [rsp+260h+var_230]
0x180024401  mov     [rbp+160h+var_148], rax
0x180024405  lea     rcx, [rbp+160h+var_158]
0x180024409  call    _lambda_59147f3b9f10595d3915fe577244bcf4___operator__
0x18002440e  mov     [rsp+260h+var_1F4], 1
0x180024416  lea     rax, [rbp+160h+var_158]
0x18002441a  mov     [rsp+260h+var_210], rax
0x18002441f  mov     rcx, [rsp+260h+var_208]
0x180024424  test    rcx, rcx
0x180024427  jnz     short loc_180024433
0x180024429  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002442e  mov     rcx, [rsp+260h+var_208]
0x180024433  mov     esi, 3
0x180024438  mov     edx, esi
0x18002443a  call    ?I_IsRoleAuthenticated@@YAHPEBUVCHANNEL_DATA@@W4_CARD_ROLE@@@Z; I_IsRoleAuthenticated(VCHANNEL_DATA const *,_CARD_ROLE)
0x18002443f  test    eax, eax
0x180024441  jnz     short loc_180024448
0x180024443  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024448  mov     al, [rsp+260h+var_228]
0x18002444c  sub     al, 80h
0x18002444e  cmp     al, 20h ; ' '
0x180024450  jbe     short loc_180024457
0x180024452  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024457  mov     dl, [rsp+260h+var_220]
0x18002445b  mov     al, dl
0x18002445d  and     al, 0Fh
0x18002445f  mov     r12d, 2
0x180024465  sub     al, r12b
0x180024468  cmp     al, sil
0x18002446b  jbe     short loc_180024476
0x18002446d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024472  mov     dl, [rsp+260h+var_220]
0x180024476  mov     [rsp+260h+hObject], r15
0x18002447b  lea     r9, [rsp+260h+hObject]
0x180024480  mov     r8, r14
0x180024483  mov     rcx, [rsp+260h+var_208]
0x180024488  mov     rcx, [rcx]
0x18002448b  call    ?I_LoadSymKeyFromBuffer@@YAKPEBUVCARD_DATA@@EAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAPEAX@Z; I_LoadSymKeyFromBuffer(VCARD_DATA const *,uchar,std::vector<uchar,wil::secure_allocator<uchar>> const &,void * *)
0x180024490  mov     [rsp+260h+var_230], eax
0x180024494  test    eax, eax
0x180024496  jz      short loc_1800244F8
0x180024498  mov     edx, r12d
0x18002449b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800244a0  lea     rax, WPP_GLOBAL_Control
0x1800244a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244ae  cmp     rcx, rax
0x1800244b1  jz      short loc_1800244EF
0x1800244b3  test    byte ptr [rcx+1Ch], 1
0x1800244b7  jz      short loc_1800244EF
0x1800244b9  cmp     [rcx+19h], r12b
0x1800244bd  jb      short loc_1800244EF
0x1800244bf  mov     edx, 58h ; 'X'
0x1800244c4  lea     rax, aUnableToLoadTh_1; "Unable to load the symmetric auth key"
0x1800244cb  mov     [rsp+260h+var_238], rax
0x1800244d0  mov     eax, [rsp+260h+var_230]
0x1800244d4  mov     [rsp+260h+var_240], eax
0x1800244d8  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800244df  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x1800244e6  mov     rcx, [rcx+10h]
0x1800244ea  call    WPP_SF_sDs
0x1800244ef  mov     edi, [rsp+260h+var_230]
0x1800244f3  jmp     loc_180024A4C
0x1800244f8  mov     dword ptr [rsp+260h+pbOutput], r15d
0x1800244fd  lea     rdx, [rsp+260h+pbOutput]; pbOutput
0x180024502  mov     rcx, [rsp+260h+hObject]; hObject
0x180024507  call    ?I_GetSymBlockSize@@YAKPEAXPEAK@Z; I_GetSymBlockSize(void *,ulong *)
0x18002450c  mov     [rsp+260h+var_230], eax
0x180024510  test    eax, eax
0x180024512  jz      short loc_180024549
0x180024514  mov     edx, r12d
0x180024517  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002451c  lea     rax, WPP_GLOBAL_Control
0x180024523  mov     rcx, cs:WPP_GLOBAL_Control
0x18002452a  cmp     rcx, rax
0x18002452d  jz      short loc_1800244EF
0x18002452f  test    byte ptr [rcx+1Ch], 1
0x180024533  jz      short loc_1800244EF
0x180024535  cmp     [rcx+19h], r12b
0x180024539  jb      short loc_1800244EF
0x18002453b  mov     edx, 59h ; 'Y'
0x180024540  lea     rax, aUnableToGetAut; "Unable to get auth algorithm block size"
0x180024547  jmp     short loc_1800244CB
0x180024549  cmp     dword ptr [rsp+260h+pbOutput], r15d
0x18002454e  ja      short loc_180024555
0x180024550  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024555  lea     rcx, [rbp+160h+var_1E0]
0x180024559  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18002455e  nop
0x18002455f  lea     rcx, [rbp+160h+var_1C8]
0x180024563  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180024568  nop
0x180024569  lea     r8, [rbp+160h+var_1E0]
0x18002456d  mov     edx, dword ptr [rsp+260h+pbOutput]
0x180024571  mov     rcx, [rsp+260h+var_208]
0x180024576  mov     rcx, [rcx]
0x180024579  call    ?I_GenerateRandomData@@YAKPEBUVCARD_DATA@@KPEAV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_GenerateRandomData(VCARD_DATA const *,ulong,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x18002457e  mov     [rsp+260h+var_230], eax
0x180024582  test    eax, eax
0x180024584  jz      short loc_1800245E6
0x180024586  mov     edx, r12d
0x180024589  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002458e  lea     rax, WPP_GLOBAL_Control
0x180024595  mov     rcx, cs:WPP_GLOBAL_Control
0x18002459c  cmp     rcx, rax
0x18002459f  jz      short loc_1800245DD
0x1800245a1  test    byte ptr [rcx+1Ch], 1
0x1800245a5  jz      short loc_1800245DD
0x1800245a7  cmp     [rcx+19h], r12b
0x1800245ab  jb      short loc_1800245DD
0x1800245ad  mov     edx, 5Ah ; 'Z'
0x1800245b2  lea     rax, aUnableToGenera_2; "Unable to generate the challenge"
0x1800245b9  mov     [rsp+260h+var_238], rax
0x1800245be  mov     eax, [rsp+260h+var_230]
0x1800245c2  mov     [rsp+260h+var_240], eax
0x1800245c6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800245cd  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x1800245d4  mov     rcx, [rcx+10h]
0x1800245d8  call    WPP_SF_sDs
0x1800245dd  mov     edi, [rsp+260h+var_230]
0x1800245e1  jmp     loc_180024A38
0x1800245e6  mov     dl, [rsp+260h+var_220]
0x1800245ea  and     dl, 7Fh
0x1800245ed  lea     r9, [rbp+160h+var_1C8]
0x1800245f1  lea     r8, [rbp+160h+var_1E0]
0x1800245f5  mov     rcx, [rsp+260h+hObject]; hObject
0x1800245fa  call    ?I_EncryptSym@@YAKPEAXEAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV12@@Z; I_EncryptSym(void *,uchar,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x1800245ff  mov     [rsp+260h+var_230], eax
0x180024603  test    eax, eax
0x180024605  jz      short loc_18002463F
0x180024607  mov     edx, r12d
0x18002460a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002460f  lea     rax, WPP_GLOBAL_Control
0x180024616  mov     rcx, cs:WPP_GLOBAL_Control
0x18002461d  cmp     rcx, rax
0x180024620  jz      short loc_1800245DD
0x180024622  test    byte ptr [rcx+1Ch], 1
0x180024626  jz      short loc_1800245DD
0x180024628  cmp     [rcx+19h], r12b
0x18002462c  jb      short loc_1800245DD
0x18002462e  mov     edx, 5Bh ; '['
0x180024633  lea     rax, aUnableToCalcul; "Unable to calculate response"
0x18002463a  jmp     loc_1800245B9
0x18002463f  mov     rcx, [rbp+160h+var_1D8]
0x180024643  sub     rcx, [rbp+160h+var_1E0]
0x180024647  mov     rax, [rbp+160h+var_1C0]
0x18002464b  sub     rax, [rbp+160h+var_1C8]
0x18002464f  cmp     rcx, rax
0x180024652  jz      short loc_180024659
0x180024654  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024659  xor     edx, edx; Val
0x18002465b  lea     r8d, [rdx+54h]; Size
0x18002465f  lea     rcx, [rbp+160h+var_B0]; void *
0x180024666  call    memset_0
0x18002466b  lea     r8, [rbp+160h+var_B0]; struct KEY_MAP_RECORD *
0x180024672  mov     dl, [rsp+260h+var_228]; unsigned __int8
0x180024676  mov     rcx, [rsp+260h+var_208]
0x18002467b  mov     rcx, [rcx]; struct VCARD_DATA *
0x18002467e  call    ?I_KeyMapGetRecord@@YAXPEBUVCARD_DATA@@EPEAUKEY_MAP_RECORD@@@Z; I_KeyMapGetRecord(VCARD_DATA const *,uchar,KEY_MAP_RECORD *)
0x180024683  lea     rcx, [rbp+160h+var_1B0]
0x180024687  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18002468c  nop
0x18002468d  mov     rcx, [rsp+260h+var_208]
0x180024692  add     rcx, 98h
0x180024699  mov     rax, [rcx+8]
0x18002469d  cmp     [rcx], rax
0x1800246a0  jz      short loc_180024715
0x1800246a2  lea     rdx, [rbp+160h+var_1B0]
0x1800246a6  call    ?I_UnprotectMemory@@YAKAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV12@@Z; I_UnprotectMemory(std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x1800246ab  mov     edi, eax
0x1800246ad  mov     [rsp+260h+var_230], eax
0x1800246b1  test    eax, eax
0x1800246b3  jz      short loc_180024719
0x1800246b5  mov     edx, r12d
0x1800246b8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800246bd  lea     rax, WPP_GLOBAL_Control
0x1800246c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246cb  cmp     rcx, rax
0x1800246ce  jz      short loc_18002470C
0x1800246d0  test    byte ptr [rcx+1Ch], 1
0x1800246d4  jz      short loc_18002470C
0x1800246d6  cmp     [rcx+19h], r12b
0x1800246da  jb      short loc_18002470C
0x1800246dc  mov     edx, 5Ch ; '\'
0x1800246e1  lea     rax, aUnableToRecove; "Unable to recover auth key"
0x1800246e8  mov     [rsp+260h+var_238], rax
0x1800246ed  mov     eax, [rsp+260h+var_230]
0x1800246f1  mov     [rsp+260h+var_240], eax
0x1800246f5  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800246fc  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180024703  mov     rcx, [rcx+10h]
0x180024707  call    WPP_SF_sDs
0x18002470c  mov     edi, [rsp+260h+var_230]
0x180024710  jmp     loc_180024A2E
0x180024715  mov     edi, [rsp+260h+var_230]
0x180024719  xor     edx, edx; Val
0x18002471b  lea     r8d, [rdx+50h]; Size
0x18002471f  lea     rcx, [rbp+160h+var_110]; void *
0x180024723  call    memset_0
0x180024728  mov     [rbp+160h+var_C0], esi
0x18002472e  mov     [rsp+260h+hKey], r15
0x180024733  mov     esi, r15d
0x180024736  cmp     esi, 0Ah
0x180024739  jnb     loc_180024808
0x18002473f  lea     rcx, [rbp+160h+var_110]; unsigned __int16 *
0x180024743  call    ?I_GenerateGuid@@YAKPEAGK@Z; I_GenerateGuid(ushort *,ulong)
0x180024748  mov     [rsp+260h+var_230], eax
0x18002474c  test    eax, eax
0x18002474e  jnz     short loc_1800247A8
0x180024750  xor     edx, edx
0x180024752  lea     rcx, [rsp+260h+hKey]
0x180024757  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18002475c  lea     rax, [rsp+260h+hKey]
0x180024761  mov     [rbp+160h+var_180], rax
0x180024765  lea     rax, [rbp+160h+var_110]
0x180024769  mov     [rsp+260h+var_1F0], rax
0x18002476e  mov     rcx, [rbx+38h]
0x180024772  test    rcx, rcx
0x180024775  jz      short loc_1800247A1
0x180024777  mov     rax, [rcx]
0x18002477a  lea     r9, [rbp+160h+var_1C8]
0x18002477e  lea     r8, [rbp+160h+var_180]
0x180024782  lea     rdx, [rsp+260h+var_1F0]
0x180024787  mov     rax, [rax+10h]
0x18002478b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024790  mov     edi, eax
0x180024792  mov     [rsp+260h+var_230], eax
0x180024796  cmp     eax, 8009000Fh
0x18002479b  jnz     short loc_180024808
0x18002479d  inc     esi
0x18002479f  jmp     short loc_180024736
0x1800247a1  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800247a7  int     3; Trap to Debugger
0x1800247a8  mov     edx, r12d
0x1800247ab  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800247b0  lea     rax, WPP_GLOBAL_Control
0x1800247b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247be  cmp     rcx, rax
0x1800247c1  jz      short loc_1800247FF
0x1800247c3  test    byte ptr [rcx+1Ch], 1
0x1800247c7  jz      short loc_1800247FF
0x1800247c9  cmp     [rcx+19h], r12b
0x1800247cd  jb      short loc_1800247FF
0x1800247cf  mov     edx, 5Dh ; ']'
0x1800247d4  lea     rax, aUnableToGenera; "Unable to generate protection key name"
0x1800247db  mov     [rsp+260h+var_238], rax
0x1800247e0  mov     eax, [rsp+260h+var_230]
0x1800247e4  mov     [rsp+260h+var_240], eax
0x1800247e8  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800247ef  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x1800247f6  mov     rcx, [rcx+10h]
0x1800247fa  call    WPP_SF_sDs
0x1800247ff  mov     edi, [rsp+260h+var_230]
0x180024803  jmp     loc_180024A23
0x180024808  test    edi, edi
0x18002480a  jz      short loc_180024841
0x18002480c  mov     edx, r12d
0x18002480f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024814  lea     rax, WPP_GLOBAL_Control
0x18002481b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024822  cmp     rcx, rax
0x180024825  jz      short loc_1800247FF
0x180024827  test    byte ptr [rcx+1Ch], 1
0x18002482b  jz      short loc_1800247FF
0x18002482d  cmp     [rcx+19h], r12b
0x180024831  jb      short loc_1800247FF
0x180024833  mov     edx, 5Eh ; '^'
0x180024838  lea     rax, aUnableToCreate_10; "Unable to create protection key within "...
0x18002483f  jmp     short loc_1800247DB
0x180024841  lea     rax, [rsp+260h+hKey]
0x180024846  mov     [rsp+260h+var_1F0], rax
0x18002484b  mov     [rsp+260h+var_1E8], 102h
  ... truncated ...
```
