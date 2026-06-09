# I_CreateCard(ushort const *,uchar,uchar,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,TPMVSC_ATTESTATION_TYPE)

- ea: `0x180016954`
- end: `0x180017441`
- name: `?I_CreateCard@@YAKPEBGEEAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@111AEBV?$vector@EV?$allocator@E@std@@@2@W4TPMVSC_ATTESTATION_TYPE@@@Z`
- size: `2797`
- prototype: `__int64 __fastcall(unsigned __int16 *, char, char, __int64, _QWORD *, _QWORD *, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `42`
- tags: `broker_com_uri`

## callers

- `0x180025b5c`
- `0x18002cfc8`

## callees

- `0x180001ec0`
- `0x1800023c0`
- `0x18000653c`
- `0x1800069b8`
- `0x18000a81c`
- `0x18000bc48`
- `0x18000bf8c`
- `0x18000c0c8`
- `0x18000c124`
- `0x18000c198`
- `0x18000d444`
- `0x18000f3a4`
- `0x18000fbe8`
- `0x18001265c`
- `0x180013e58`
- `0x180015ca8`
- `0x180016164`
- `0x1800161e0`
- `0x1800162d0`
- `0x180016324`
- `0x180016560`
- `0x18001669c`
- `0x18001670c`
- `0x18001676c`
- `0x18001679c`
- `0x1800167c8`
- `0x1800167f4`
- `0x180016880`
- `0x1800168d4`
- `0x180016954`
- `0x180017860`
- `0x18001f288`
- `0x18001f42c`
- `0x18001f784`
- `0x1800225a0`
- `0x180028250`
- `0x180028610`
- `0x180028e48`
- `0x1800297cc`
- `0x18002aa64`
- `0x18002b378`
- `0x1800348a0`

## import_xrefs

- `TpmCoreProvisioning!TpmDeleteOwnerAuth` at `0x180017346`
- `TpmCoreProvisioning!TpmDeleteOwnerAuth` at `0x180017346`

## string_xrefs

- `0x180016ef5`: `Unable to create blobs folder`
- `0x1800169b9`: `I_CreateCard`
- `0x180016aca`: `Unable to set card root path`
- `0x180016c79`: `Failed to open channel`
- `0x180016ce4`: `PIN does not meet complexity requirement`
- `0x180016d7e`: `PUK does not meet complexity requirement`
- `0x180016e9b`: `Unable to create validation key`
- `0x180017434`: `Unable to create AIK`

## pseudocode

```c
__int64 __fastcall I_CreateCard(
        unsigned __int16 *a1,
        char a2,
        char a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        __int64 a7,
        __int64 a8,
        int a9)
{
  __int64 v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  int v15; // edx
  const char *v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // ebx
  void *v19; // rax
  PIN_MAPS_MEM *v20; // rax
  PIN_MAPS_MEM *v21; // rdx
  __int64 v22; // rcx
  _QWORD *v23; // rcx
  int v24; // edx
  const char *v25; // rax
  __int64 v26; // rcx
  const unsigned __int16 *v27; // rdx
  __int64 v28; // rcx
  int v29; // edi
  _QWORD *v30; // rcx
  int v31; // edx
  const char *v32; // rax
  unsigned int v33; // edi
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rax
  int v38; // r8d
  int v39; // edx
  _QWORD *v40; // rcx
  int v41; // edx
  const char *v42; // rax
  __int64 v43; // rcx
  unsigned int Dir; // edi
  PVOID v45; // rcx
  __int64 v46; // rcx
  _QWORD *v47; // rcx
  int v48; // edx
  const char *v49; // rax
  __int64 v50; // rcx
  int v51; // edx
  __int64 v52; // rcx
  int v53; // r8d
  int v54; // r9d
  _QWORD *v55; // rcx
  int v56; // edx
  const char *v57; // rax
  __int64 v58; // rcx
  __int64 v59; // rcx
  _QWORD *v60; // rcx
  int v61; // edx
  const char *v62; // rax
  __int64 v63; // rcx
  char v64; // di
  __int64 v65; // rcx
  int v66; // r9d
  int v67; // eax
  void *v68; // rdx
  unsigned int v69; // r8d
  int pszKeyName; // [rsp+20h] [rbp-E0h]
  int Guid; // [rsp+40h] [rbp-C0h] BYREF
  char v73; // [rsp+48h] [rbp-B8h] BYREF
  struct VCHANNEL_DATA *v74; // [rsp+50h] [rbp-B0h] BYREF
  char v75[8]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v76; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v77; // [rsp+68h] [rbp-98h]
  struct VCHANNEL_DATA **v78; // [rsp+70h] [rbp-90h] BYREF
  __int16 v79; // [rsp+78h] [rbp-88h]
  struct VCHANNEL_DATA **v80; // [rsp+80h] [rbp-80h] BYREF
  __int16 v81; // [rsp+88h] [rbp-78h]
  int v82; // [rsp+90h] [rbp-70h] BYREF
  struct VCHANNEL_DATA **v83; // [rsp+98h] [rbp-68h] BYREF
  __int16 v84; // [rsp+A0h] [rbp-60h]
  struct VCHANNEL_DATA **v85; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v86; // [rsp+B0h] [rbp-50h]
  _BYTE v87[24]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v88[24]; // [rsp+D0h] [rbp-30h] BYREF
  struct VCHANNEL_DATA **v89; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v90[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v91; // [rsp+100h] [rbp+0h]
  _QWORD v92[2]; // [rsp+108h] [rbp+8h] BYREF
  __int16 v93; // [rsp+118h] [rbp+18h]
  _QWORD *v94; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v95[3]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v96[2]; // [rsp+140h] [rbp+40h] BYREF
  int v97; // [rsp+150h] [rbp+50h]
  struct KEY_MAPS_MEM *v98; // [rsp+180h] [rbp+80h] BYREF
  PIN_MAPS_MEM *v99; // [rsp+190h] [rbp+90h]
  __int32 v100; // [rsp+1B8h] [rbp+B8h] BYREF
  char v101[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v73 = a2;
  Guid = 0;
  v82 = 0;
  strcpy(v101, "I_CreateCard");
  v95[0] = v101;
  v95[1] = &v82;
  v95[2] = &Guid;
  lambda_d12730a2778e42de870b5614ba373850_::operator()(v95);
  v82 = 1;
  v94 = v95;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (unsigned __int8)(v73 + 0x80) > 0x20u )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (unsigned __int8)((a3 & 0xF) - 2) > 3u )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v12 = a5[1];
  if ( *a5 != v12 && v12 - *a5 != 3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  VCARD_DATA::VCARD_DATA((VCARD_DATA *)v96);
  v96[0] = I_InternalAlloc;
  v96[1] = I_InternalFree;
  v97 = 0;
  _InterlockedExchange(&v100, 0);
  Guid = I_SetVCardRoot((struct VCARD_DATA *)v96, a1);
  if ( !Guid )
  {
    Guid = I_InitializeProviders((struct VCARD_DATA *)v96);
    if ( Guid )
    {
      WppTraceIndent(v17, 2);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      v15 = 12;
      v16 = "Unable to initialize algorithm providers";
      goto LABEL_20;
    }
    v76 = v96;
    v77 = 258;
    v19 = operator new(0xB24u);
    std::unique_ptr<KEY_MAPS_MEM>::reset(&v98, v19);
    I_KeyMapInitialize(v98);
    v89 = (struct VCHANNEL_DATA **)operator new(0x130u);
    v20 = PIN_MAPS_MEM::PIN_MAPS_MEM((PIN_MAPS_MEM *)v89);
    v21 = v99;
    v99 = v20;
    if ( v21 )
    {
      std::default_delete<PIN_MAPS_MEM>::operator()();
      v20 = v99;
    }
    Guid = I_PinMapInitialize(a8, v20);
    if ( Guid )
    {
      WppTraceIndent(v22, 2);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v24 = 13;
      v25 = "Unable to initialize PIN map";
LABEL_29:
      WPP_SF_sDs(
        v23[2],
        v24,
        (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
        (_DWORD)WPP_pszIndent,
        Guid,
        (__int64)v25);
LABEL_30:
      v18 = Guid;
LABEL_135:
      wil::details::ScopeExitFnGuard__lambda_875cd6c6c30062f5969e3f9667d80d00___::operator()(&v76);
      goto LABEL_136;
    }
    v97 = 1;
    v74 = 0;
    Guid = I_VChannelOpen((struct VCARD_DATA *)v96, &v74);
    if ( Guid )
    {
      WppTraceIndent(v26, 2);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v24 = 14;
      v25 = "Failed to open channel";
      goto LABEL_29;
    }
    v78 = &v74;
    v79 = 258;
    if ( !(unsigned int)I_PinMapValidatePinComplexity(*(_QWORD *)v74, 1, a7) )
    {
      WppTraceIndent(v28, 2);
      v29 = -2146435068;
      Guid = -2146435068;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_42;
      }
      v31 = 15;
      v32 = "PIN does not meet complexity requirement";
LABEL_41:
      WPP_SF_sDs(
        v30[2],
        v31,
        (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
        (_DWORD)WPP_pszIndent,
        4,
        (__int64)v32);
      v29 = Guid;
LABEL_42:
      wil::details::ScopeExitFnGuard__lambda_8df077a85f71db72a9008d311a7eeac9___::operator()(&v78);
      wil::details::ScopeExitFnGuard__lambda_875cd6c6c30062f5969e3f9667d80d00___::operator()(&v76);
      v18 = v29;
      goto LABEL_136;
    }
    if ( *a6 != a6[1] && !(unsigned int)I_PinMapValidatePinComplexity(*(_QWORD *)v74, 2, a6) )
    {
      WppTraceIndent(v28, 2);
      v29 = -2146435068;
      Guid = -2146435068;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_42;
      }
      v31 = 16;
      v32 = "PUK does not meet complexity requirement";
      goto LABEL_41;
    }
    v33 = 0;
    v34 = Guid;
    while ( v33 < 0xA )
    {
      Guid = I_GenerateGuid(*(unsigned __int16 **)(*(_QWORD *)v74 + 64LL), (unsigned int)v27);
      if ( Guid )
      {
        WppTraceIndent(v36, 2);
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v41 = 17;
          v42 = "Unable to generate validation key name";
          goto LABEL_58;
        }
        goto LABEL_59;
      }
      v75[0] = 48;
      v37 = std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
              v92,
              v35,
              v75);
      LOBYTE(v38) = 4;
      LOBYTE(v39) = 71;
      Guid = I_CreateKspKey(*(_QWORD *)v74, v39, v38, 0, *(LPCWSTR *)(*(_QWORD *)v74 + 64LL), v37, 0);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v92);
      v34 = Guid;
      if ( Guid != -2146893809 )
        break;
      ++v33;
    }
    if ( v34 )
    {
      WppTraceIndent(v28, 2);
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v41 = 18;
        v42 = "Unable to create validation key";
LABEL_58:
        WPP_SF_sDs(
          v40[2],
          v41,
          (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
          (_DWORD)WPP_pszIndent,
          Guid,
          (__int64)v42);
      }
LABEL_59:
      v18 = Guid;
      goto LABEL_134;
    }
    v80 = &v74;
    v81 = 258;
    Dir = I_CreateDir(*(const struct VCARD_DATA **)v74, v27);
    if ( Dir )
    {
      WppTraceIndent(v43, 2);
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
          (_DWORD)WPP_pszIndent,
          Dir,
          (__int64)"Unable to create blobs folder");
      }
      Guid = Dir;
      WppTraceIndent(v45, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
          (_DWORD)WPP_pszIndent,
          Guid,
          (__int64)"Creating blobs folder failed");
      }
      v18 = Guid;
LABEL_133:
      wil::details::ScopeExitFnGuard__lambda_3ce46cd70d36682ee9b5fe2e17b515bb___::operator()(&v80);
LABEL_134:
      wil::details::ScopeExitFnGuard__lambda_8df077a85f71db72a9008d311a7eeac9___::operator()(&v78);
      goto LABEL_135;
    }
    Guid = 0;
    v83 = &v74;
    v84 = 258;
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v88);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v87);
    Guid = I_CreateAuthKey(*(_QWORD *)v74, v88);
    if ( Guid )
    {
      WppTraceIndent(v46, 2);
      v47 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_81;
      }
      v48 = 21;
      v49 = "Unable to generate auth key";
LABEL_80:
      WPP_SF_sDs(
        v47[2],
        v48,
        (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
        (_DWORD)WPP_pszIndent,
        Guid,
        (__int64)v49);
LABEL_81:
      v18 = Guid;
LABEL_132:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v87);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v88);
      wil::details::ScopeExitFnGuard__lambda_453ceae959c35823d90fbc184cc22f70___::operator()(&v83);
      goto LABEL_133;
    }
    Guid = I_ProtectMemory(v88, v87);
    if ( Guid )
    {
      WppTraceIndent(v50, 2);
      v47 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_81;
      }
      v48 = 22;
      v49 = "Unable to protect auth key";
      goto LABEL_80;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=((char *)v74 + 128, v87);
    *((_DWORD *)v74 + 16) = 3;
    v85 = &v74;
    v86 = 258;
    Guid = I_SetReferenceData(v74, 1, a7);
    if ( Guid )
    {
      WppTraceIndent(v52, 2);
      v55 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_93;
      }
      v56 = 23;
      v57 = "Unable to set PIN";
LABEL_92:
      WPP_SF_sDs(
        v55[2],
        v56,
        (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
        (_DWORD)WPP_pszIndent,
        Guid,
        (__int64)v57);
LABEL_93:
      v18 = Guid;
LABEL_131:
      wil::details::ScopeExitFnGuard__lambda_dff2f22c6c37664c95078b9cc3eb9222___::operator()(&v85);
      goto LABEL_132;
    }
    if ( *a6 != a6[1] )
    {
      Guid = I_SetReferenceData(v74, 2, a6);
      if ( Guid )
      {
        WppTraceIndent(v58, 2);
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_93;
        }
        v56 = 24;
        v57 = "Unable to set PUK";
        goto LABEL_92;
      }
    }
    v90[0] = &v74;
    v90[1] = &v73;
    v91 = 258;
    if ( *a6 == a6[1] )
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=((char *)v74 + 152, (char *)v74 + 128);
    LOBYTE(v54) = 1;
    LOBYTE(v53) = a3;
    LOBYTE(v51) = v73;
    Guid = I_ImportSymKeyLocking((_DWORD)v74, v51, v53, v54, a4, (__int64)a5);
    if ( Guid )
    {
      WppTraceIndent(v59, 2);
      v60 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_108;
      }
      v61 = 25;
      v62 = "Unable to import admin key";
LABEL_107:
      WPP_SF_sDs(
        v60[2],
        v61,
        (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
        (_DWORD)WPP_pszIndent,
        Guid,
        (__int64)v62);
LABEL_108:
      v18 = Guid;
LABEL_130:
      wil::details::ScopeExitFnGuard__lambda_e0b0c0a212a2174da9781c493ac85f53___::operator()(v90);
      goto LABEL_131;
    }
    v89 = &v74;
    Guid = lambda_c174b0374f76a55c4a474eed7bf99d64_::operator()(&v89);
    if ( Guid )
    {
      WppTraceIndent(v63, 2);
      v60 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_108;
      }
      v61 = 29;
      v62 = "Saving mapping files failed";
      goto LABEL_107;
    }
    v64 = 0;
    if ( !a9 )
    {
      WppTraceIndent(v63, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids);
      }
      v64 = 1;
      a9 = 2;
    }
    Guid = I_CreateAikLocking(v74);
    if ( Guid )
    {
      WppTraceIndent(v65, 2);
      if ( !v64 )
      {
        v60 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_108;
        }
        v61 = 32;
        v62 = "Unable to create AIK";
        goto LABEL_107;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
          v66,
          Guid);
      }
      Guid = 0;
      a9 = 0;
    }
    v92[0] = &v74;
    v92[1] = &a9;
    v93 = 258;
    v67 = TpmDeleteOwnerAuth();
    if ( v67 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, v68, v69, (const char *)(unsigned int)v67, pszKeyName);
    HIBYTE(v81) = 0;
    HIBYTE(v91) = 0;
    HIBYTE(v86) = 0;
    HIBYTE(v84) = 0;
    HIBYTE(v93) = 0;
    v18 = Guid;
    wil::details::ScopeExitFnGuard__lambda_e765e349f178dc617a44a42808e5213e___::operator()(v92);
    goto LABEL_130;
  }
  WppTraceIndent(v13, 2);
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_21;
  }
  v15 = 11;
  v16 = "Unable to set card root path";
LABEL_20:
  WPP_SF_sDs(
    v14[2],
    v15,
    (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
    (_DWORD)WPP_pszIndent,
    Guid,
    (__int64)v16);
LABEL_21:
  v18 = Guid;
LABEL_136:
  VCARD_DATA::~VCARD_DATA((VCARD_DATA *)v96);
  WppTraceUnwinder__lambda_d12730a2778e42de870b5614ba373850____::_WppTraceUnwinder__lambda_d12730a2778e42de870b5614ba373850____(&v94);
  return v18;
}

```

## disassembly

```asm
0x180016954  push    rbp
0x180016956  push    rbx
0x180016957  push    rsi
0x180016958  push    rdi
0x180016959  push    r12
0x18001695b  push    r13
0x18001695d  push    r14
0x18001695f  push    r15
0x180016961  lea     rbp, [rsp-0E8h]
0x180016969  sub     rsp, 1E8h
0x180016970  mov     rax, cs:__security_cookie
0x180016977  xor     rax, rsp
0x18001697a  mov     [rbp+120h+var_50], rax
0x180016981  mov     r13, r9
0x180016984  mov     r15b, r8b
0x180016987  mov     rdi, rcx
0x18001698a  mov     [rsp+220h+var_1D8], dl
0x18001698e  mov     r14, [rbp+120h+arg_20]
0x180016995  mov     rbx, [rbp+120h+arg_28]
0x18001699c  mov     r12, [rbp+120h+arg_30]
0x1800169a3  mov     rsi, [rbp+120h+arg_38]
0x1800169aa  mov     [rsp+220h+var_1E0], 0
0x1800169b2  mov     [rbp+120h+var_190], 0
0x1800169b9  movsd   xmm0, qword ptr cs:aICreatecard; "I_CreateCard"
0x1800169c1  movsd   qword ptr [rbp+120h+var_60], xmm0
0x1800169c9  mov     eax, dword ptr cs:aICreatecard+8; "Card"
0x1800169cf  mov     dword ptr [rbp+120h+var_60+8], eax
0x1800169d5  mov     al, byte ptr cs:aICreatecard+0Ch; ""
0x1800169db  mov     [rbp+120h+var_60+0Ch], al
0x1800169e1  lea     rax, [rbp+120h+var_60]
0x1800169e8  mov     [rbp+120h+var_F8], rax
0x1800169ec  lea     rax, [rbp+120h+var_190]
0x1800169f0  mov     [rbp+120h+var_F0], rax
0x1800169f4  lea     rax, [rsp+220h+var_1E0]
0x1800169f9  mov     [rbp+120h+var_E8], rax
0x1800169fd  lea     rcx, [rbp+120h+var_F8]
0x180016a01  call    _lambda_d12730a2778e42de870b5614ba373850___operator__
0x180016a06  mov     [rbp+120h+var_190], 1
0x180016a0d  lea     rax, [rbp+120h+var_F8]
0x180016a11  mov     [rbp+120h+var_100], rax
0x180016a15  test    rdi, rdi
0x180016a18  jnz     short loc_180016A1F
0x180016a1a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180016a1f  mov     al, [rsp+220h+var_1D8]
0x180016a23  sub     al, 80h
0x180016a25  cmp     al, 20h ; ' '
0x180016a27  jbe     short loc_180016A2E
0x180016a29  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180016a2e  mov     al, r15b
0x180016a31  and     al, 0Fh
0x180016a33  sub     al, 2
0x180016a35  cmp     al, 3
0x180016a37  jbe     short loc_180016A3E
0x180016a39  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180016a3e  mov     rax, [r14+8]
0x180016a42  cmp     [r14], rax
0x180016a45  jz      short loc_180016A55
0x180016a47  sub     rax, [r14]
0x180016a4a  cmp     rax, 3
0x180016a4e  jz      short loc_180016A55
0x180016a50  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180016a55  lea     rcx, [rbp+120h+var_E0]; this
0x180016a59  call    ??0VCARD_DATA@@QEAA@XZ; VCARD_DATA::VCARD_DATA(void)
0x180016a5e  nop
0x180016a5f  lea     rax, ?I_InternalAlloc@@YAPEAX_K@Z; I_InternalAlloc(unsigned __int64)
0x180016a66  mov     [rbp+120h+var_E0], rax
0x180016a6a  lea     rax, ?I_InternalFree@@YAXPEAX@Z; I_InternalFree(void *)
0x180016a71  mov     [rbp+120h+var_D8], rax
0x180016a75  mov     [rbp+120h+var_D0], 0
0x180016a7c  xor     eax, eax
0x180016a7e  xchg    eax, [rbp+120h+var_68]
0x180016a84  mov     rdx, rdi; unsigned __int16 *
0x180016a87  lea     rcx, [rbp+120h+var_E0]; struct VCARD_DATA *
0x180016a8b  call    ?I_SetVCardRoot@@YAKPEAUVCARD_DATA@@PEBG@Z; I_SetVCardRoot(VCARD_DATA *,ushort const *)
0x180016a90  mov     [rsp+220h+var_1E0], eax
0x180016a94  test    eax, eax
0x180016a96  jz      short loc_180016AD3
0x180016a98  mov     edx, 2
0x180016a9d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016aa2  lea     rbx, WPP_GLOBAL_Control
0x180016aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ab0  cmp     rcx, rbx
0x180016ab3  jz      loc_180016B3D
0x180016ab9  test    byte ptr [rcx+1Ch], 1
0x180016abd  jz      short loc_180016B3D
0x180016abf  cmp     byte ptr [rcx+19h], 2
0x180016ac3  jb      short loc_180016B3D
0x180016ac5  mov     edx, 0Bh
0x180016aca  lea     rax, aUnableToSetCar; "Unable to set card root path"
0x180016ad1  jmp     short loc_180016B19
0x180016ad3  lea     rcx, [rbp+120h+var_E0]; struct VCARD_DATA *
0x180016ad7  call    ?I_InitializeProviders@@YAKPEAUVCARD_DATA@@@Z; I_InitializeProviders(VCARD_DATA *)
0x180016adc  mov     [rsp+220h+var_1E0], eax
0x180016ae0  test    eax, eax
0x180016ae2  jz      short loc_180016B46
0x180016ae4  mov     edx, 2
0x180016ae9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016aee  lea     rbx, WPP_GLOBAL_Control
0x180016af5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016afc  cmp     rcx, rbx
0x180016aff  jz      short loc_180016B3D
0x180016b01  test    byte ptr [rcx+1Ch], 1
0x180016b05  jz      short loc_180016B3D
0x180016b07  cmp     byte ptr [rcx+19h], 2
0x180016b0b  jb      short loc_180016B3D
0x180016b0d  mov     edx, 0Ch
0x180016b12  lea     rax, aUnableToInitia_0; "Unable to initialize algorithm provider"...
0x180016b19  mov     [rsp+220h+var_1F8], rax
0x180016b1e  mov     eax, [rsp+220h+var_1E0]
0x180016b22  mov     dword ptr [rsp+220h+pszKeyName], eax
0x180016b26  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180016b2d  lea     r8, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids
0x180016b34  mov     rcx, [rcx+10h]
0x180016b38  call    WPP_SF_sDs
0x180016b3d  mov     ebx, [rsp+220h+var_1E0]
0x180016b41  jmp     loc_1800173D3
0x180016b46  lea     rax, [rbp+120h+var_E0]
0x180016b4a  mov     [rsp+220h+var_1C0], rax
0x180016b4f  mov     edi, 2
0x180016b54  mov     [rsp+220h+var_1B8], 102h
0x180016b5b  mov     ecx, 0B24h; Size
0x180016b60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016b65  mov     rdx, rax
0x180016b68  lea     rcx, [rbp+120h+var_A0]
0x180016b6f  call    ?reset@?$unique_ptr@UKEY_MAPS_MEM@@U?$default_delete@UKEY_MAPS_MEM@@@std@@@std@@QEAAXPEAUKEY_MAPS_MEM@@@Z; std::unique_ptr<KEY_MAPS_MEM>::reset(KEY_MAPS_MEM *)
0x180016b74  mov     rcx, [rbp+120h+var_A0]; struct KEY_MAPS_MEM *
0x180016b7b  call    ?I_KeyMapInitialize@@YAXPEAUKEY_MAPS_MEM@@@Z; I_KeyMapInitialize(KEY_MAPS_MEM *)
0x180016b80  mov     ecx, 130h; Size
0x180016b85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016b8a  mov     [rbp+120h+var_138], rax
0x180016b8e  mov     rcx, rax; this
0x180016b91  call    ??0PIN_MAPS_MEM@@QEAA@XZ; PIN_MAPS_MEM::PIN_MAPS_MEM(void)
0x180016b96  nop
0x180016b97  mov     rdx, [rbp+120h+var_90]
0x180016b9e  mov     [rbp+120h+var_90], rax
0x180016ba5  test    rdx, rdx
0x180016ba8  jz      short loc_180016BB6
0x180016baa  call    ??R?$default_delete@UPIN_MAPS_MEM@@@std@@QEBAXPEAUPIN_MAPS_MEM@@@Z; std::default_delete<PIN_MAPS_MEM>::operator()(PIN_MAPS_MEM *)
0x180016baf  mov     rax, [rbp+120h+var_90]
0x180016bb6  mov     rdx, rax
0x180016bb9  mov     rcx, rsi
0x180016bbc  call    ?I_PinMapInitialize@@YAKAEBV?$vector@EV?$allocator@E@std@@@std@@PEAUPIN_MAPS_MEM@@@Z; I_PinMapInitialize(std::vector<uchar> const &,PIN_MAPS_MEM *)
0x180016bc1  mov     [rsp+220h+var_1E0], eax
0x180016bc5  test    eax, eax
0x180016bc7  jz      short loc_180016C28
0x180016bc9  mov     edx, edi
0x180016bcb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016bd0  lea     rbx, WPP_GLOBAL_Control
0x180016bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bde  cmp     rcx, rbx
0x180016be1  jz      short loc_180016C1F
0x180016be3  test    byte ptr [rcx+1Ch], 1
0x180016be7  jz      short loc_180016C1F
0x180016be9  cmp     [rcx+19h], dil
0x180016bed  jb      short loc_180016C1F
0x180016bef  mov     edx, 0Dh
0x180016bf4  lea     rax, aUnableToInitia_1; "Unable to initialize PIN map"
0x180016bfb  mov     [rsp+220h+var_1F8], rax
0x180016c00  mov     eax, [rsp+220h+var_1E0]
0x180016c04  mov     dword ptr [rsp+220h+pszKeyName], eax
0x180016c08  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180016c0f  lea     r8, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids
0x180016c16  mov     rcx, [rcx+10h]
0x180016c1a  call    WPP_SF_sDs
0x180016c1f  mov     ebx, [rsp+220h+var_1E0]
0x180016c23  jmp     loc_1800173C8
0x180016c28  mov     [rbp+120h+var_D0], 1
0x180016c2f  mov     [rsp+220h+var_1D0], 0
0x180016c38  lea     rdx, [rsp+220h+var_1D0]; struct VCHANNEL_DATA **
0x180016c3d  lea     rcx, [rbp+120h+var_E0]; struct VCARD_DATA *
0x180016c41  call    ?I_VChannelOpen@@YAKPEAUVCARD_DATA@@PEAPEAUVCHANNEL_DATA@@@Z; I_VChannelOpen(VCARD_DATA *,VCHANNEL_DATA * *)
0x180016c46  mov     [rsp+220h+var_1E0], eax
0x180016c4a  test    eax, eax
0x180016c4c  jz      short loc_180016C85
0x180016c4e  mov     edx, edi
0x180016c50  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016c55  lea     rbx, WPP_GLOBAL_Control
0x180016c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c63  cmp     rcx, rbx
0x180016c66  jz      short loc_180016C1F
0x180016c68  test    byte ptr [rcx+1Ch], 1
0x180016c6c  jz      short loc_180016C1F
0x180016c6e  cmp     [rcx+19h], dil
0x180016c72  jb      short loc_180016C1F
0x180016c74  mov     edx, 0Eh
0x180016c79  lea     rax, aFailedToOpenCh; "Failed to open channel"
0x180016c80  jmp     loc_180016BFB
0x180016c85  lea     rax, [rsp+220h+var_1D0]
0x180016c8a  mov     [rsp+220h+var_1B0], rax
0x180016c8f  mov     esi, 2
0x180016c94  mov     [rsp+220h+var_1A8], 102h
0x180016c9b  mov     r8, r12
0x180016c9e  lea     edx, [rsi-1]
0x180016ca1  mov     rcx, [rsp+220h+var_1D0]
0x180016ca6  mov     rcx, [rcx]
0x180016ca9  call    ?I_PinMapValidatePinComplexity@@YAHPEBUVCARD_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_PinMapValidatePinComplexity(VCARD_DATA const *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x180016cae  test    eax, eax
0x180016cb0  jnz     short loc_180016D2B
0x180016cb2  mov     edx, esi
0x180016cb4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016cb9  mov     edi, 80100004h
0x180016cbe  mov     [rsp+220h+var_1E0], edi
0x180016cc2  lea     rbx, WPP_GLOBAL_Control
0x180016cc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cd0  cmp     rcx, rbx
0x180016cd3  jz      short loc_180016D0F
0x180016cd5  test    byte ptr [rcx+1Ch], 1
0x180016cd9  jz      short loc_180016D0F
0x180016cdb  cmp     [rcx+19h], sil
0x180016cdf  jb      short loc_180016D0F
0x180016ce1  lea     edx, [rsi+0Dh]
0x180016ce4  lea     rax, aPinDoesNotMeet; "PIN does not meet complexity requiremen"...
0x180016ceb  mov     [rsp+220h+var_1F8], rax
0x180016cf0  mov     dword ptr [rsp+220h+pszKeyName], edi
0x180016cf4  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180016cfb  lea     r8, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids
0x180016d02  mov     rcx, [rcx+10h]
0x180016d06  call    WPP_SF_sDs
0x180016d0b  mov     edi, [rsp+220h+var_1E0]
0x180016d0f  lea     rcx, [rsp+220h+var_1B0]
0x180016d14  call    wil__details__ScopeExitFnGuard__lambda_8df077a85f71db72a9008d311a7eeac9_____operator__
0x180016d19  nop
0x180016d1a  lea     rcx, [rsp+220h+var_1C0]
0x180016d1f  call    wil__details__ScopeExitFnGuard__lambda_875cd6c6c30062f5969e3f9667d80d00_____operator__
0x180016d24  mov     ebx, edi
0x180016d26  jmp     loc_1800173D3
0x180016d2b  mov     rax, [rbx+8]
0x180016d2f  cmp     [rbx], rax
0x180016d32  jz      short loc_180016D8A
0x180016d34  mov     r8, rbx
0x180016d37  mov     edx, esi
0x180016d39  mov     rcx, [rsp+220h+var_1D0]
0x180016d3e  mov     rcx, [rcx]
0x180016d41  call    ?I_PinMapValidatePinComplexity@@YAHPEBUVCARD_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_PinMapValidatePinComplexity(VCARD_DATA const *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x180016d46  test    eax, eax
0x180016d48  jnz     short loc_180016D8A
0x180016d4a  mov     edx, esi
0x180016d4c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016d51  mov     edi, 80100004h
0x180016d56  mov     [rsp+220h+var_1E0], edi
0x180016d5a  lea     rbx, WPP_GLOBAL_Control
0x180016d61  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d68  cmp     rcx, rbx
0x180016d6b  jz      short loc_180016D0F
0x180016d6d  test    byte ptr [rcx+1Ch], 1
0x180016d71  jz      short loc_180016D0F
0x180016d73  cmp     [rcx+19h], sil
0x180016d77  jb      short loc_180016D0F
0x180016d79  mov     edx, 10h
0x180016d7e  lea     rax, aPukDoesNotMeet; "PUK does not meet complexity requiremen"...
0x180016d85  jmp     loc_180016CEB
0x180016d8a  xor     edi, edi
0x180016d8c  mov     eax, [rsp+220h+var_1E0]
0x180016d90  cmp     edi, 0Ah
0x180016d93  jnb     loc_180016E6C
0x180016d99  mov     rax, [rsp+220h+var_1D0]
0x180016d9e  mov     rcx, [rax]
0x180016da1  mov     rcx, [rcx+40h]; unsigned __int16 *
0x180016da5  call    ?I_GenerateGuid@@YAKPEAGK@Z; I_GenerateGuid(ushort *,ulong)
0x180016daa  mov     [rsp+220h+var_1E0], eax
0x180016dae  test    eax, eax
0x180016db0  jnz     short loc_180016E0D
0x180016db2  mov     [rsp+220h+var_1C8], 30h ; '0'
0x180016db7  lea     r8, [rsp+220h+var_1C8]
0x180016dbc  lea     rcx, [rbp+120h+var_118]
0x180016dc0  call    ??$?0U?$secure_allocator@E@wil@@$0A@@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBEAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,uchar const &,wil::secure_allocator<uchar> const &)
0x180016dc5  nop
0x180016dc6  mov     rcx, [rsp+220h+var_1D0]
0x180016dcb  mov     rcx, [rcx]; int
0x180016dce  mov     [rsp+220h+var_1F0], 0; int
0x180016dd6  mov     [rsp+220h+var_1F8], rax; __int64
0x180016ddb  mov     rax, [rcx+40h]
0x180016ddf  mov     [rsp+220h+pszKeyName], rax; pszKeyName
0x180016de4  xor     r9d, r9d; int
0x180016de7  mov     r8b, 4; int
0x180016dea  mov     dl, 47h ; 'G'; int
0x180016dec  call    ?I_CreateKspKey@@YAKPEBUVCARD_DATA@@EEPEA_KPEBGAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@H@Z; I_CreateKspKey(VCARD_DATA const *,uchar,uchar,unsigned __int64 *,ushort const *,std::vector<uchar,wil::secure_allocator<uchar>> const &,int)
0x180016df1  mov     [rsp+220h+var_1E0], eax
0x180016df5  lea     rcx, [rbp+120h+var_118]
0x180016df9  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180016dfe  mov     eax, [rsp+220h+var_1E0]
0x180016e02  cmp     eax, 8009000Fh
0x180016e07  jnz     short loc_180016E6C
0x180016e09  inc     edi
0x180016e0b  jmp     short loc_180016D90
0x180016e0d  mov     edx, esi
0x180016e0f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016e14  lea     rbx, WPP_GLOBAL_Control
0x180016e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e22  cmp     rcx, rbx
0x180016e25  jz      short loc_180016E63
0x180016e27  test    byte ptr [rcx+1Ch], 1
0x180016e2b  jz      short loc_180016E63
0x180016e2d  cmp     [rcx+19h], sil
0x180016e31  jb      short loc_180016E63
0x180016e33  mov     edx, 11h
0x180016e38  lea     rax, aUnableToGenera_1; "Unable to generate validation key name"
0x180016e3f  mov     [rsp+220h+var_1F8], rax
0x180016e44  mov     eax, [rsp+220h+var_1E0]
0x180016e48  mov     dword ptr [rsp+220h+pszKeyName], eax
  ... truncated ...
```
