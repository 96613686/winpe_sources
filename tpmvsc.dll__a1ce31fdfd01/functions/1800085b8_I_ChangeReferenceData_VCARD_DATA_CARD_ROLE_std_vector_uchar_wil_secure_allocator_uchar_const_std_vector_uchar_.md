# I_ChangeReferenceData(VCARD_DATA *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &)

- ea: `0x1800085b8`
- end: `0x180008c34`
- name: `?I_ChangeReferenceData@@YAKPEAUVCARD_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@2@Z`
- size: `1660`
- prototype: `__int64 __fastcall(struct VCARD_DATA *, unsigned int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008324`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x18000675c`
- `0x1800068dc`
- `0x18000735c`
- `0x18000794c`
- `0x180007988`
- `0x1800085b8`
- `0x180008d28`
- `0x18000bc48`
- `0x18000c010`
- `0x18000c198`
- `0x1800121dc`
- `0x1800123c4`
- `0x180012580`
- `0x18001280c`
- `0x1800128c4`
- `0x180013434`
- `0x180013814`
- `0x18001e9a8`
- `0x18001eadc`
- `0x1800201f0`
- `0x1800203fc`
- `0x180028250`
- `0x1800348a0`

## string_xrefs

- `0x180008ade`: `Unable to update user record`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_ChangeReferenceData(struct VCARD_DATA *a1, unsigned int a2, __int64 a3, _DWORD *a4)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rcx
  unsigned int v9; // esi
  _QWORD *v10; // rcx
  int v11; // edx
  const char *v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // edx
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  int v17; // edx
  const char *v18; // rax
  unsigned int v19; // ebx
  unsigned int v20; // eax
  NCRYPT_KEY_HANDLE hKey; // rdi
  __int64 v22; // rcx
  unsigned __int8 v23; // dl
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  int v26; // edx
  const char *v27; // rax
  unsigned int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  unsigned int v33; // esi
  PVOID v34; // rcx
  unsigned int Handle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v37; // [rsp+38h] [rbp-C8h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  struct VCARD_DATA *v39; // [rsp+48h] [rbp-B8h] BYREF
  NCRYPT_KEY_HANDLE p_hObject; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v41; // [rsp+58h] [rbp-A8h]
  int v42; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v43; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v44[3]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v45; // [rsp+88h] [rbp-78h]
  _QWORD v46[4]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v47[40]; // [rsp+B0h] [rbp-50h] BYREF
  int v48; // [rsp+100h] [rbp+0h]
  int v49; // [rsp+104h] [rbp+4h]
  int InitialRetryCount; // [rsp+108h] [rbp+8h]
  unsigned __int16 v51[48]; // [rsp+110h] [rbp+10h] BYREF
  char v52[24]; // [rsp+170h] [rbp+70h] BYREF

  v39 = a1;
  v37 = a2;
  Handle = 0;
  v42 = 0;
  strcpy(v52, "I_ChangeReferenceData");
  v46[0] = v52;
  v46[1] = &v42;
  v46[2] = &Handle;
  lambda_ac61bcaa84bd93f4aecf9d8635734642_::operator()(v46);
  v42 = 1;
  v43 = v46;
  if ( !v39 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5);
  v7 = v37;
  if ( v37 - 1 > 1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5);
    v7 = v37;
  }
  memset_0(v51, 0, 0x5Cu);
  I_PinMapGetRecord(v39, v7, v51);
  if ( !(unsigned int)I_PinMapIsActive((const struct PIN_MAP_RECORD *)v51) )
  {
    WppTraceIndent(v8, 2);
    v9 = -2146435038;
    Handle = -2146435038;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_77;
    }
    v11 = 100;
    v12 = "Role is not active";
    goto LABEL_15;
  }
  if ( (unsigned int)I_PinMapIsBlocked((const struct PIN_MAP_RECORD *)v51) )
  {
    WppTraceIndent(v13, 2);
    v9 = -2146434964;
    Handle = -2146434964;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_77;
    }
    v11 = 101;
    v12 = "The role has been blocked";
LABEL_15:
    WPP_SF_sDs(
      v10[2],
      v11,
      (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
      (_DWORD)WPP_pszIndent,
      v9,
      (__int64)v12);
    v9 = Handle;
    goto LABEL_77;
  }
  memset_0(v47, 0, 0x5Cu);
  v48 = 1;
  v49 = a4[2] - *a4;
  InitialRetryCount = I_PinMapGetInitialRetryCount(v37);
  memset_0(v47, 0, sizeof(v47));
  hObject = 0;
  p_hObject = 0;
  Handle = I_PinMapGetHandle(v39, v37, &p_hObject);
  if ( Handle )
  {
    WppTraceIndent(v15, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 102;
      v18 = "Unable to get smart card key of the role";
LABEL_21:
      WPP_SF_sDs(
        v16[2],
        v17,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        Handle,
        (__int64)v18);
    }
    goto LABEL_22;
  }
  v19 = 0;
  v20 = 0;
  hKey = p_hObject;
  while ( 1 )
  {
    if ( v19 >= 0xA )
    {
LABEL_32:
      if ( v20 )
      {
        WppTraceIndent(v15, 2);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = 104;
          v18 = "Unable to duplicate the smart card key";
          goto LABEL_21;
        }
        goto LABEL_22;
      }
      p_hObject = (NCRYPT_KEY_HANDLE)&hObject;
      v41 = 258;
      Handle = I_AuthenticateKspKey(hObject);
      if ( Handle )
      {
        WppTraceIndent(v24, 2);
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_43;
        }
        v26 = 105;
        v27 = "Unable to authenticate the key using the old PIN";
      }
      else
      {
        v28 = I_ChangePasswordKspKey(hObject);
        Handle = v28;
        v9 = -2146434965;
        if ( v28 == -2146434965 )
        {
          Handle = I_DecreaseRemainingRetryCount(v39, v37);
          if ( !Handle )
          {
            WppTraceIndent(v30, 2);
            Handle = -2146434965;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_75;
            }
            WPP_SF_sDs(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              107,
              (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
              (_DWORD)WPP_pszIndent,
              107,
              (__int64)"Changing PIN failed");
LABEL_43:
            v9 = Handle;
LABEL_75:
            wil::details::ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f___::operator()(&p_hObject);
            goto LABEL_76;
          }
          WppTraceIndent(v30, 2);
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_43;
          }
          v26 = 106;
          v27 = "Failed to reduce remaining retry count";
        }
        else if ( v28 )
        {
          WppTraceIndent(v29, 2);
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_43;
          }
          v26 = 108;
          v27 = "Unable to change key password";
        }
        else
        {
          Handle = I_PinMapSetRecord(v39, v37, v47);
          if ( !Handle )
          {
            v44[0] = &v39;
            v44[1] = &v37;
            v44[2] = v51;
            v45 = 258;
            v33 = I_PinMapSave(v39);
            if ( v33 )
            {
              WppTraceIndent(v32, 2);
              v34 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_sDs(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  110,
                  (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
                  (_DWORD)WPP_pszIndent,
                  v33,
                  (__int64)"Unable to store PIN maps");
              }
              Handle = v33;
              WppTraceIndent(v34, 2);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_sDs(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  111,
                  (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
                  (_DWORD)WPP_pszIndent,
                  Handle,
                  (__int64)"Changing password and updating PIN map file failed");
              }
            }
            else
            {
              Handle = 0;
              HIBYTE(v41) = 0;
              HIBYTE(v45) = 0;
              I_DeleteKspKey(v39, v51);
            }
            v9 = Handle;
            wil::details::ScopeExitFnGuard__lambda_f38f1c235d4bbfc7af7b18896877faaa___::operator()(v44);
            goto LABEL_75;
          }
          WppTraceIndent(v31, 2);
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_43;
          }
          v26 = 109;
          v27 = "Unable to update user record";
        }
      }
      WPP_SF_sDs(
        v25[2],
        v26,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        Handle,
        (__int64)v27);
      goto LABEL_43;
    }
    Handle = I_GenerateGuid(v47, v14);
    if ( Handle )
      break;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &hObject,
      0);
    v20 = I_DuplicateKspKey(v39, v23, &hObject, v47, hKey);
    Handle = v20;
    if ( v20 != -2146893809 )
      goto LABEL_32;
    ++v19;
  }
  WppTraceIndent(v22, 2);
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = 103;
    v18 = "Generating GUID failed";
    goto LABEL_21;
  }
LABEL_22:
  v9 = Handle;
LABEL_76:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
LABEL_77:
  WppTraceUnwinder__lambda_ac61bcaa84bd93f4aecf9d8635734642____::_WppTraceUnwinder__lambda_ac61bcaa84bd93f4aecf9d8635734642____(&v43);
  return v9;
}

```

## disassembly

```asm
0x1800085b8  push    rbp
0x1800085ba  push    rbx
0x1800085bb  push    rsi
0x1800085bc  push    rdi
0x1800085bd  push    r14
0x1800085bf  push    r15
0x1800085c1  lea     rbp, [rsp-98h]
0x1800085c9  sub     rsp, 198h
0x1800085d0  mov     rax, cs:__security_cookie
0x1800085d7  xor     rax, rsp
0x1800085da  mov     [rbp+0C0h+var_38], rax
0x1800085e1  mov     rsi, r9
0x1800085e4  mov     r14, r8
0x1800085e7  mov     [rsp+1C0h+var_178], rcx
0x1800085ec  mov     [rsp+1C0h+var_188], edx
0x1800085f0  mov     [rsp+1C0h+var_190], 0
0x1800085f8  mov     [rsp+1C0h+var_160], 0
0x180008600  movups  xmm0, xmmword ptr cs:aIChangereferen; "I_ChangeReferenceData"
0x180008607  movups  xmmword ptr [rbp+0C0h+var_50], xmm0
0x18000860b  movsd   xmm1, qword ptr cs:aIChangereferen+0Eh; "nceData"
0x180008613  movsd   qword ptr [rbp+0C0h+var_50+0Eh], xmm1
0x180008618  lea     rax, [rbp+0C0h+var_50]
0x18000861c  mov     [rbp+0C0h+var_130], rax
0x180008620  lea     rax, [rsp+1C0h+var_160]
0x180008625  mov     [rbp+0C0h+var_128], rax
0x180008629  lea     rax, [rsp+1C0h+var_190]
0x18000862e  mov     [rbp+0C0h+var_120], rax
0x180008632  lea     rcx, [rbp+0C0h+var_130]
0x180008636  call    _lambda_ac61bcaa84bd93f4aecf9d8635734642___operator__
0x18000863b  mov     r15d, 1
0x180008641  mov     [rsp+1C0h+var_160], r15d
0x180008646  lea     rax, [rbp+0C0h+var_130]
0x18000864a  mov     [rsp+1C0h+var_158], rax
0x18000864f  cmp     [rsp+1C0h+var_178], 0
0x180008655  jnz     short loc_18000865C
0x180008657  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000865c  mov     ebx, [rsp+1C0h+var_188]
0x180008660  lea     eax, [rbx-1]
0x180008663  cmp     eax, r15d
0x180008666  jbe     short loc_180008671
0x180008668  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000866d  mov     ebx, [rsp+1C0h+var_188]
0x180008671  mov     edi, 5Ch ; '\'
0x180008676  mov     r8d, edi; Size
0x180008679  xor     edx, edx; Val
0x18000867b  lea     rcx, [rbp+0C0h+var_B0]; void *
0x18000867f  call    memset_0
0x180008684  lea     r8, [rbp+0C0h+var_B0]
0x180008688  mov     edx, ebx
0x18000868a  mov     rcx, [rsp+1C0h+var_178]
0x18000868f  call    ?I_PinMapGetRecord@@YAXPEBUVCARD_DATA@@W4_CARD_ROLE@@PEAUPIN_MAP_RECORD@@@Z; I_PinMapGetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD *)
0x180008694  lea     rcx, [rbp+0C0h+var_B0]; struct PIN_MAP_RECORD *
0x180008698  call    ?I_PinMapIsActive@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsActive(PIN_MAP_RECORD const *)
0x18000869d  test    eax, eax
0x18000869f  jnz     short loc_1800086EA
0x1800086a1  lea     ebx, [rdi-5Ah]
0x1800086a4  mov     edx, ebx
0x1800086a6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800086ab  mov     esi, 80100022h
0x1800086b0  mov     [rsp+1C0h+var_190], esi
0x1800086b4  lea     rdi, WPP_GLOBAL_Control
0x1800086bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086c2  cmp     rcx, rdi
0x1800086c5  jz      loc_180008C09
0x1800086cb  test    [rcx+1Ch], r15b
0x1800086cf  jz      loc_180008C09
0x1800086d5  cmp     [rcx+19h], bl
0x1800086d8  jb      loc_180008C09
0x1800086de  lea     edx, [rbx+62h]
0x1800086e1  lea     rax, aRoleIsNotActiv; "Role is not active"
0x1800086e8  jmp     short loc_180008740
0x1800086ea  lea     rcx, [rbp+0C0h+var_B0]; struct PIN_MAP_RECORD *
0x1800086ee  call    ?I_PinMapIsBlocked@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsBlocked(PIN_MAP_RECORD const *)
0x1800086f3  test    eax, eax
0x1800086f5  jz      short loc_180008769
0x1800086f7  mov     ebx, 2
0x1800086fc  mov     edx, ebx
0x1800086fe  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008703  mov     esi, 8010006Ch
0x180008708  mov     [rsp+1C0h+var_190], esi
0x18000870c  lea     rdi, WPP_GLOBAL_Control
0x180008713  mov     rcx, cs:WPP_GLOBAL_Control
0x18000871a  cmp     rcx, rdi
0x18000871d  jz      loc_180008C09
0x180008723  test    [rcx+1Ch], r15b
0x180008727  jz      loc_180008C09
0x18000872d  cmp     [rcx+19h], bl
0x180008730  jb      loc_180008C09
0x180008736  lea     edx, [rbx+63h]
0x180008739  lea     rax, aTheRoleHasBeen; "The role has been blocked"
0x180008740  mov     [rsp+1C0h+var_198], rax
0x180008745  mov     dword ptr [rsp+1C0h+hKey], esi
0x180008749  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180008750  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x180008757  mov     rcx, [rcx+10h]
0x18000875b  call    WPP_SF_sDs
0x180008760  mov     esi, [rsp+1C0h+var_190]
0x180008764  jmp     loc_180008C09
0x180008769  mov     r8, rdi; Size
0x18000876c  xor     edx, edx; Val
0x18000876e  lea     rcx, [rbp+0C0h+var_110]; void *
0x180008772  call    memset_0
0x180008777  mov     [rbp+0C0h+var_C0], r15d
0x18000877b  mov     eax, [rsi+8]
0x18000877e  sub     eax, [rsi]
0x180008780  mov     [rbp+0C0h+var_BC], eax
0x180008783  mov     ecx, [rsp+1C0h+var_188]
0x180008787  call    ?I_PinMapGetInitialRetryCount@@YAJW4_CARD_ROLE@@@Z; I_PinMapGetInitialRetryCount(_CARD_ROLE)
0x18000878c  mov     [rbp+0C0h+var_B8], eax
0x18000878f  xor     edx, edx; Val
0x180008791  lea     r8d, [rdx+50h]; Size
0x180008795  lea     rcx, [rbp+0C0h+var_110]; void *
0x180008799  call    memset_0
0x18000879e  mov     [rsp+1C0h+hObject], 0
0x1800087a7  mov     [rsp+1C0h+var_170], 0
0x1800087b0  lea     r8, [rsp+1C0h+var_170]
0x1800087b5  mov     edx, [rsp+1C0h+var_188]
0x1800087b9  mov     rcx, [rsp+1C0h+var_178]
0x1800087be  call    ?I_PinMapGetHandle@@YAKPEBUVCARD_DATA@@W4_CARD_ROLE@@PEA_K@Z; I_PinMapGetHandle(VCARD_DATA const *,_CARD_ROLE,unsigned __int64 *)
0x1800087c3  mov     [rsp+1C0h+var_190], eax
0x1800087c7  test    eax, eax
0x1800087c9  jz      short loc_18000882C
0x1800087cb  mov     ebx, 2
0x1800087d0  mov     edx, ebx
0x1800087d2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800087d7  lea     rdi, WPP_GLOBAL_Control
0x1800087de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087e5  cmp     rcx, rdi
0x1800087e8  jz      short loc_180008823
0x1800087ea  test    [rcx+1Ch], r15b
0x1800087ee  jz      short loc_180008823
0x1800087f0  cmp     [rcx+19h], bl
0x1800087f3  jb      short loc_180008823
0x1800087f5  lea     edx, [rbx+64h]
0x1800087f8  lea     rax, aUnableToGetSma; "Unable to get smart card key of the rol"...
0x1800087ff  mov     [rsp+1C0h+var_198], rax
0x180008804  mov     eax, [rsp+1C0h+var_190]
0x180008808  mov     dword ptr [rsp+1C0h+hKey], eax
0x18000880c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180008813  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000881a  mov     rcx, [rcx+10h]
0x18000881e  call    WPP_SF_sDs
0x180008823  mov     esi, [rsp+1C0h+var_190]
0x180008827  jmp     loc_180008BFE
0x18000882c  xor     ebx, ebx
0x18000882e  xor     eax, eax
0x180008830  mov     rdi, [rsp+1C0h+var_170]
0x180008835  cmp     ebx, 0Ah
0x180008838  jnb     loc_1800088C4
0x18000883e  lea     rcx, [rbp+0C0h+var_110]; unsigned __int16 *
0x180008842  call    ?I_GenerateGuid@@YAKPEAGK@Z; I_GenerateGuid(ushort *,ulong)
0x180008847  mov     [rsp+1C0h+var_190], eax
0x18000884b  test    eax, eax
0x18000884d  jnz     short loc_180008883
0x18000884f  xor     edx, edx
0x180008851  lea     rcx, [rsp+1C0h+hObject]
0x180008856  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18000885b  mov     [rsp+1C0h+hKey], rdi; hKey
0x180008860  lea     r9, [rbp+0C0h+var_110]; unsigned __int16 *
0x180008864  lea     r8, [rsp+1C0h+hObject]; unsigned __int64 *
0x180008869  mov     rcx, [rsp+1C0h+var_178]; struct VCARD_DATA *
0x18000886e  call    ?I_DuplicateKspKey@@YAKPEBUVCARD_DATA@@EPEA_KPEBG_K@Z; I_DuplicateKspKey(VCARD_DATA const *,uchar,unsigned __int64 *,ushort const *,unsigned __int64)
0x180008873  mov     [rsp+1C0h+var_190], eax
0x180008877  cmp     eax, 8009000Fh
0x18000887c  jnz     short loc_1800088C4
0x18000887e  add     ebx, r15d
0x180008881  jmp     short loc_180008835
0x180008883  mov     ebx, 2
0x180008888  mov     edx, ebx
0x18000888a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000888f  lea     rdi, WPP_GLOBAL_Control
0x180008896  mov     rcx, cs:WPP_GLOBAL_Control
0x18000889d  cmp     rcx, rdi
0x1800088a0  jz      short loc_180008823
0x1800088a2  test    [rcx+1Ch], r15b
0x1800088a6  jz      loc_180008823
0x1800088ac  cmp     [rcx+19h], bl
0x1800088af  jb      loc_180008823
0x1800088b5  lea     edx, [rbx+65h]
0x1800088b8  lea     rax, aGeneratingGuid; "Generating GUID failed"
0x1800088bf  jmp     loc_1800087FF
0x1800088c4  mov     ebx, 2
0x1800088c9  test    eax, eax
0x1800088cb  jz      short loc_18000890D
0x1800088cd  mov     edx, ebx
0x1800088cf  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800088d4  lea     rdi, WPP_GLOBAL_Control
0x1800088db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088e2  cmp     rcx, rdi
0x1800088e5  jz      loc_180008823
0x1800088eb  test    [rcx+1Ch], r15b
0x1800088ef  jz      loc_180008823
0x1800088f5  cmp     [rcx+19h], bl
0x1800088f8  jb      loc_180008823
0x1800088fe  lea     edx, [rbx+66h]
0x180008901  lea     rax, aUnableToDuplic; "Unable to duplicate the smart card key"
0x180008908  jmp     loc_1800087FF
0x18000890d  lea     rax, [rsp+1C0h+hObject]
0x180008912  mov     [rsp+1C0h+var_170], rax
0x180008917  mov     [rsp+1C0h+var_168], 102h
0x18000891e  mov     rdx, r14
0x180008921  mov     rcx, [rsp+1C0h+hObject]; hObject
0x180008926  call    ?I_AuthenticateKspKey@@YAK_KAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_AuthenticateKspKey(unsigned __int64,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x18000892b  mov     [rsp+1C0h+var_190], eax
0x18000892f  test    eax, eax
0x180008931  jz      short loc_180008991
0x180008933  mov     edx, ebx
0x180008935  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000893a  lea     rdi, WPP_GLOBAL_Control
0x180008941  mov     rcx, cs:WPP_GLOBAL_Control
0x180008948  cmp     rcx, rdi
0x18000894b  jz      short loc_180008988
0x18000894d  test    [rcx+1Ch], r15b
0x180008951  jz      short loc_180008988
0x180008953  cmp     [rcx+19h], bl
0x180008956  jb      short loc_180008988
0x180008958  mov     edx, 69h ; 'i'
0x18000895d  lea     rax, aUnableToAuthen_1; "Unable to authenticate the key using th"...
0x180008964  mov     [rsp+1C0h+var_198], rax
0x180008969  mov     eax, [rsp+1C0h+var_190]
0x18000896d  mov     dword ptr [rsp+1C0h+hKey], eax
0x180008971  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180008978  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000897f  mov     rcx, [rcx+10h]
0x180008983  call    WPP_SF_sDs
0x180008988  mov     esi, [rsp+1C0h+var_190]
0x18000898c  jmp     loc_180008BF3
0x180008991  mov     rdx, rsi
0x180008994  mov     rcx, [rsp+1C0h+hObject]; hObject
0x180008999  call    ?I_ChangePasswordKspKey@@YAK_KAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_ChangePasswordKspKey(unsigned __int64,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x18000899e  mov     [rsp+1C0h+var_190], eax
0x1800089a2  mov     esi, 8010006Bh
0x1800089a7  cmp     eax, esi
0x1800089a9  jnz     loc_180008A48
0x1800089af  mov     edx, [rsp+1C0h+var_188]
0x1800089b3  mov     rcx, [rsp+1C0h+var_178]
0x1800089b8  call    I_DecreaseRemainingRetryCount
0x1800089bd  mov     [rsp+1C0h+var_190], eax
0x1800089c1  mov     edx, ebx
0x1800089c3  test    eax, eax
0x1800089c5  jz      short loc_1800089FB
0x1800089c7  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800089cc  lea     rdi, WPP_GLOBAL_Control
0x1800089d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089da  cmp     rcx, rdi
0x1800089dd  jz      short loc_180008988
0x1800089df  test    [rcx+1Ch], r15b
0x1800089e3  jz      short loc_180008988
0x1800089e5  cmp     [rcx+19h], bl
0x1800089e8  jb      short loc_180008988
0x1800089ea  mov     edx, 6Ah ; 'j'
0x1800089ef  lea     rax, aFailedToReduce; "Failed to reduce remaining retry count"
0x1800089f6  jmp     loc_180008964
0x1800089fb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008a00  mov     [rsp+1C0h+var_190], esi
0x180008a04  lea     rdi, WPP_GLOBAL_Control
0x180008a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a12  cmp     rcx, rdi
0x180008a15  jz      loc_180008BF3
0x180008a1b  test    [rcx+1Ch], r15b
0x180008a1f  jz      loc_180008BF3
0x180008a25  cmp     [rcx+19h], bl
0x180008a28  jb      loc_180008BF3
0x180008a2e  mov     edx, 6Bh ; 'k'
0x180008a33  lea     rax, aChangingPinFai; "Changing PIN failed"
0x180008a3a  mov     [rsp+1C0h+var_198], rax
0x180008a3f  mov     dword ptr [rsp+1C0h+hKey], esi
0x180008a43  jmp     loc_180008971
0x180008a48  test    eax, eax
0x180008a4a  jz      short loc_180008A8E
0x180008a4c  mov     edx, ebx
0x180008a4e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008a53  lea     rdi, WPP_GLOBAL_Control
0x180008a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a61  cmp     rcx, rdi
0x180008a64  jz      loc_180008988
0x180008a6a  test    [rcx+1Ch], r15b
0x180008a6e  jz      loc_180008988
0x180008a74  cmp     [rcx+19h], bl
0x180008a77  jb      loc_180008988
0x180008a7d  mov     edx, 6Ch ; 'l'
0x180008a82  lea     rax, aUnableToChange_0; "Unable to change key password"
0x180008a89  jmp     loc_180008964
0x180008a8e  lea     r8, [rbp+0C0h+var_110]
0x180008a92  mov     edx, [rsp+1C0h+var_188]
0x180008a96  mov     rcx, [rsp+1C0h+var_178]
0x180008a9b  call    ?I_PinMapSetRecord@@YAKPEBUVCARD_DATA@@W4_CARD_ROLE@@PEBUPIN_MAP_RECORD@@@Z; I_PinMapSetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD const *)
0x180008aa0  mov     [rsp+1C0h+var_190], eax
0x180008aa4  test    eax, eax
0x180008aa6  jz      short loc_180008AEA
0x180008aa8  mov     edx, ebx
0x180008aaa  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008aaf  lea     rdi, WPP_GLOBAL_Control
0x180008ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x180008abd  cmp     rcx, rdi
0x180008ac0  jz      loc_180008988
0x180008ac6  test    [rcx+1Ch], r15b
0x180008aca  jz      loc_180008988
0x180008ad0  cmp     [rcx+19h], bl
0x180008ad3  jb      loc_180008988
  ... truncated ...
```
