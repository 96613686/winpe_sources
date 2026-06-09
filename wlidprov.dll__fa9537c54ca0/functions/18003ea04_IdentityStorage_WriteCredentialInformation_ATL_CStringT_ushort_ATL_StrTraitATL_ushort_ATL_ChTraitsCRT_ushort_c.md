# IdentityStorage::WriteCredentialInformation(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_ModernIdentityType,ulong,ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>> const &,ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>> const &,bool)

- ea: `0x18003ea04`
- end: `0x18003f0ef`
- name: `?WriteCredentialInformation@IdentityStorage@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0W4_ModernIdentityType@@KAEBV?$CAtlArray@UIdentityToken@@V?$CElementTraits@UIdentityToken@@@ATL@@@3@AEBV?$CAtlArray@UIdentityProperty@@V?$CElementTraits@UIdentityProperty@@@ATL@@@3@_N@Z`
- size: `1771`
- prototype: `__int64 __usercall@<rax>(IdentityStorage *this@<rcx>, unsigned __int8, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003f0f8`

## callees

- `0x180002eb4`
- `0x180003054`
- `0x1800035cc`
- `0x180003990`
- `0x180003cf0`
- `0x180004824`
- `0x180004910`
- `0x180004b00`
- `0x180004b44`
- `0x1800061a8`
- `0x180006aa4`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x180010adc`
- `0x180010b80`
- `0x1800125dc`
- `0x180012e74`
- `0x180013434`
- `0x180016010`
- `0x18001606c`
- `0x180016c0c`
- `0x180017064`
- `0x18003c3b0`
- `0x18003c5f4`
- `0x18003c624`
- `0x18003c650`
- `0x18003c808`
- `0x18003db58`
- `0x18003ea04`
- `0x18003f44c`
- `0x18003f5c0`

## string_xrefs

- `0x18003ea3b`: `IdentityStorage::WriteCredentialInformation`
- `0x18003ecba`: `IdentityStorage::WriteCredentialInformation`
- `0x18003f058`: `IdentityStorage::WriteCredentialInformation`
- `0x18003eb5f`: `hr = WritePairwiseId(defaultId, applicationId, identityPropertyArray[i].Value)`
- `0x18003eca8`: `tempTokenArray.SetCount(tokenArray.GetCount())`
- `0x18003ec64`: `hr = WriteProperties(defaultId, userScopedProperties)`
- `0x18003ee75`: `hr = SerializeObjectWithVersion(tokenbagSerializer, tokenBag, CurrentSerializationVersion, &apTokenBagBuffer, &encodedSize)`
- `0x18003f005`: `hr = registryHelper.WriteBufferToRegistry(nullptr, registryKey, GetIdentityKey(identityType), REG_SZ, reinterpret_cast<BYTE*>(const_cast<LPWSTR>(static_cast<LPCWSTR>(defaultId))), (defaultId.GetLength() + 1) * sizeof(WCHAR))`
- `0x18003efab`: `hr = registryHelper.WriteBufferToRegistry(nullptr, registryKey, static_cast<LPCWSTR>(valueForTicketKey), REG_BINARY, apTokenBagBuffer, encodedSize)`
- `0x18003f046`: `hr = registryHelper.WriteBufferToRegistry(nullptr, registryKey, ApplicationFlags, REG_DWORD, reinterpret_cast<BYTE*>(&applicationFlags), sizeof(applicationFlags))`
- `0x18003edc5`: `Software\Microsoft\IdentityCRL\Immersive\%s\Token\`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall IdentityStorage::WriteCredentialInformation(
        IdentityStorage *this,
        const unsigned __int16 **a2,
        const unsigned __int16 **a3,
        unsigned int a4,
        unsigned __int8 a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  const unsigned __int16 **v9; // r14
  unsigned __int64 v11; // rdi
  __int64 i; // rsi
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  unsigned int v16; // r8d
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  int *v20; // r14
  __int64 v21; // rbx
  char v22; // r15
  const char *v23; // rcx
  __int64 v24; // rsi
  __int64 v25; // rbx
  unsigned int v26; // r15d
  __int64 v27; // rbx
  __int64 v28; // rbx
  __int64 v29; // rbx
  __int64 v30; // rbx
  __int64 v31; // rbx
  __int64 EnvironmentSpecificRegistryKey; // rax
  __int64 v33; // rdx
  unsigned __int16 *v34; // rbx
  int *v35; // rdi
  __int64 v36; // rbx
  int v37; // r8d
  __int64 v38; // rcx
  __int64 v39; // rax
  _QWORD *v40; // rax
  char v41; // si
  unsigned int v42; // r12d
  __int64 IdentityTokenKey; // rax
  unsigned __int16 *v44; // rcx
  unsigned __int16 *v45; // rdi
  int *v46; // r14
  __int64 v47; // rdi
  __int64 v48; // rcx
  unsigned __int16 *v49; // rsi
  unsigned int v50; // edi
  const unsigned __int16 *IdentityKey; // rax
  unsigned int v52; // ebx
  char *v54; // [rsp+28h] [rbp-E0h]
  char *v55; // [rsp+28h] [rbp-E0h]
  __int64 v56; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v57[2]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int16 *v58; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 *v59; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+70h] [rbp-98h] BYREF
  __int64 v61; // [rsp+78h] [rbp-90h]
  __int64 v62; // [rsp+80h] [rbp-88h]
  int v63; // [rsp+88h] [rbp-80h]
  __int64 v64; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int8 *v65; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v66[8]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v67; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v68; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v69[3]; // [rsp+C0h] [rbp-48h] BYREF
  int v70; // [rsp+D8h] [rbp-30h]
  int *v71[4]; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v72[11]; // [rsp+100h] [rbp-8h] BYREF
  int v73; // [rsp+168h] [rbp+60h] BYREF
  const unsigned __int16 **v74; // [rsp+170h] [rbp+68h]
  unsigned int v75; // [rsp+180h] [rbp+78h]

  v75 = a4;
  v74 = a2;
  v9 = a2;
  v73 = 0;
  v72[0] = "IdentityStorage::WriteCredentialInformation";
  v72[1] = &v73;
  v72[2] = 0;
  v72[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
    "IdentityStorage::WriteCredentialInformation",
    (const char *)0x156,
    0,
    (const unsigned __int16 *)v54);
  v67 = *(_QWORD *)this;
  v65 = 0;
  v57[0] = 0;
  v64 = v67;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v59);
  v68 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  memset(v69, 0, sizeof(v69));
  v70 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v56);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v58);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v71,
    "IdentityStorage::WriteCredentialInformation",
    &v73,
    0xBu,
    &qword_18006F818);
  v11 = 0;
  for ( i = a7; v11 < *(_QWORD *)(i + 8); ++v11 )
  {
    v13 = ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](i, v11);
    if ( (unsigned __int8)ATL::operator==(v13, L"PWID") )
    {
      if ( *(_DWORD *)(*(_QWORD *)(ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](
                                     i,
                                     v11)
                                 + 8)
                     - 16LL) )
      {
        v14 = ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](i, v11);
        v15 = IdentityStorage::WritePairwiseId(this, *a3, *v9, *(const unsigned __int16 **)(v14 + 8));
        v73 = v15;
        if ( v15 < 0 )
        {
          v55 = "hr = WritePairwiseId(defaultId, applicationId, identityPropertyArray[i].Value)";
          v16 = 365;
          goto LABEL_57;
        }
      }
    }
    else
    {
      v17 = ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](i, v11);
      ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::Add(v69, v17);
      v18 = ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](i, v11);
      if ( (unsigned __int8)ATL::operator==(v18, L"AuthMembername") )
      {
        v19 = *(_QWORD *)(ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](
                            i,
                            v11)
                        + 8);
        v20 = (int *)(v56 - 24);
        if ( v19 - 24 != v56 - 24 )
        {
          if ( v20[4] >= 0 && *(_QWORD *)(v19 - 24) == *(_QWORD *)v20 )
          {
            v21 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
            ATL::CStringData::Release((ATL::CStringData *)v20);
            v56 = v21 + 24;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v56, v19, *(unsigned int *)(v19 - 16));
          }
        }
        v9 = v74;
      }
    }
  }
  v22 = a8;
  if ( a8 != 1 || *(_DWORD *)(v56 - 16) )
  {
    v15 = IdentityStorage::WriteProperties(this, *a3, v69);
    v73 = v15;
    if ( v15 >= 0 )
    {
      v24 = a6;
      v25 = *(_QWORD *)(a6 + 8);
      if ( v25 )
      {
        if ( !(unsigned __int8)ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::GrowBuffer(
                                 &v60,
                                 *(_QWORD *)(a6 + 8)) )
        {
          v73 = -2147024882;
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
            "IdentityStorage::WriteCredentialInformation",
            0x187u,
            -2147024882,
            "tempTokenArray.SetCount(tokenArray.GetCount())");
          goto LABEL_58;
        }
        ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::CallConstructors();
      }
      else
      {
        v62 = 0;
      }
      v61 = v25;
      LODWORD(v68) = v25;
      LODWORD(a7) = 0;
      if ( (_DWORD)v25 )
      {
        v26 = a7;
        do
        {
          v27 = *(_QWORD *)ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](v24, v26);
          *(_QWORD *)ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::operator[](&v60, v26) = v27;
          v28 = *(_QWORD *)(ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](v24, v26) + 8);
          *(_QWORD *)(ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::operator[](&v60, v26) + 8) = v28;
          LODWORD(v28) = *(_DWORD *)(ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](
                                       v24,
                                       v26)
                                   + 16);
          *(_DWORD *)(ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::operator[](&v60, v26) + 16) = v28;
          v29 = *(_QWORD *)(ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](v24, v26) + 24);
          *(_QWORD *)(ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::operator[](&v60, v26) + 24) = v29;
          v30 = *(_QWORD *)(ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](v24, v26) + 32);
          *(_QWORD *)(ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::operator[](&v60, v26) + 32) = v30;
          v31 = *(_QWORD *)(ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](v24, v26) + 40);
          *(_QWORD *)(ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::operator[](&v60, v26++) + 40) = v31;
        }
        while ( v26 < (unsigned int)v68 );
        v22 = a8;
      }
      *((_QWORD *)&v68 + 1) = v60;
      EnvironmentSpecificRegistryKey = IdentityStorage::GetEnvironmentSpecificRegistryKey(
                                         this,
                                         v66,
                                         L"Software\\Microsoft\\IdentityCRL\\Immersive\\%s\\Token\\");
      v33 = *(_QWORD *)ATL::operator+(&a7, EnvironmentSpecificRegistryKey, v9);
      v34 = v59;
      v35 = (int *)(v59 - 12);
      if ( (unsigned __int16 *)(v33 - 24) != v59 - 12 )
      {
        if ( v35[4] >= 0 && *(_QWORD *)(v33 - 24) == *(_QWORD *)v35 )
        {
          v36 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
          ATL::CStringData::Release((ATL::CStringData *)v35);
          v34 = (unsigned __int16 *)(v36 + 24);
          v59 = v34;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v59, v33, *(unsigned int *)(v33 - 16));
          v34 = v59;
        }
      }
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&a7);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v66);
      v15 = SerializeObjectWithVersion<ModernAppTokenBagSerializer,_ModernAppTokenBag>(
              (unsigned int)&v67,
              (unsigned int)&v68,
              v37,
              (unsigned int)&v65,
              (__int64)v57);
      v73 = v15;
      if ( v15 >= 0 )
      {
        if ( v22 == 1 )
        {
          v39 = ATL::operator+(v66, a3, L"|");
          v40 = (_QWORD *)ATL::operator+(&v67, v39, &v56);
          v41 = 3;
          v42 = v75;
        }
        else
        {
          v42 = v75;
          IdentityTokenKey = IdentityStorage::GetIdentityTokenKey(v38, v75);
          v40 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                            &a7,
                            IdentityTokenKey);
          v41 = 4;
        }
        v44 = (unsigned __int16 *)(*v40 - 24LL);
        v45 = v58;
        v46 = (int *)(v58 - 12);
        if ( v44 != v58 - 12 )
        {
          if ( v46[4] >= 0 && *(_QWORD *)v44 == *(_QWORD *)v46 )
          {
            v47 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
            ATL::CStringData::Release((ATL::CStringData *)v46);
            v45 = (unsigned __int16 *)(v47 + 24);
            v58 = v45;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v58, *v40, *(unsigned int *)(*v40 - 16LL));
            v45 = v58;
          }
        }
        if ( (v41 & 4) != 0 )
        {
          v41 &= ~4u;
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&a7);
        }
        if ( (v41 & 2) != 0 )
        {
          v41 &= ~2u;
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v67);
        }
        if ( (v41 & 1) != 0 )
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v66);
        v15 = RegistryHelper::WriteBufferToRegistry((RegistryHelper *)&v64, 0, v34, v45, 3u, v65, v57[0]);
        v73 = v15;
        if ( v15 >= 0 )
        {
          if ( v22 )
            goto LABEL_58;
          v49 = (unsigned __int16 *)*a3;
          v50 = 2 * *((_DWORD *)*a3 - 4) + 2;
          IdentityKey = (const unsigned __int16 *)IdentityStorage::GetIdentityKey(v48, v42);
          v15 = RegistryHelper::WriteBufferToRegistry(
                  (RegistryHelper *)&v64,
                  0,
                  v34,
                  IdentityKey,
                  1u,
                  (unsigned __int8 *)v49,
                  v50);
          v73 = v15;
          if ( v15 >= 0 )
          {
            v15 = RegistryHelper::WriteBufferToRegistry(
                    (RegistryHelper *)&v64,
                    0,
                    v34,
                    L"ApplicationFlags",
                    4u,
                    &a5,
                    4u);
            v73 = v15;
            if ( v15 >= 0 )
              goto LABEL_58;
            v23 = "hr = registryHelper.WriteBufferToRegistry(nullptr, registryKey, ApplicationFlags, REG_DWORD, reinterpr"
                  "et_cast<BYTE*>(&applicationFlags), sizeof(applicationFlags))";
            v16 = 442;
          }
          else
          {
            v23 = "hr = registryHelper.WriteBufferToRegistry(nullptr, registryKey, GetIdentityKey(identityType), REG_SZ, "
                  "reinterpret_cast<BYTE*>(const_cast<LPWSTR>(static_cast<LPCWSTR>(defaultId))), (defaultId.GetLength() +"
                  " 1) * sizeof(WCHAR))";
            v16 = 434;
          }
        }
        else
        {
          v23 = "hr = registryHelper.WriteBufferToRegistry(nullptr, registryKey, static_cast<LPCWSTR>(valueForTicketKey),"
                " REG_BINARY, apTokenBagBuffer, encodedSize)";
          v16 = 423;
        }
      }
      else
      {
        v23 = "hr = SerializeObjectWithVersion(tokenbagSerializer, tokenBag, CurrentSerializationVersion, &apTokenBagBuff"
              "er, &encodedSize)";
        v16 = 411;
      }
    }
    else
    {
      v23 = "hr = WriteProperties(defaultId, userScopedProperties)";
      v16 = 388;
    }
    v55 = (char *)v23;
LABEL_57:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      "IdentityStorage::WriteCredentialInformation",
      v16,
      v15,
      v55);
  }
  else
  {
    TracePrintW(
      3u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      0x180u,
      L"Member name was empty for a secondary account.");
  }
LABEL_58:
  v52 = v73;
  ErrorVerifier::CheckAgainstList((const char *)v71[3], *v71[2], (unsigned __int64)v71[1], v71[0]);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v56);
  ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::~CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>(v69);
  ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::~CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>(&v60);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
  CMIDLPtr<unsigned short *>::Clear(&v65);
  CTraceFuncW<long>::~CTraceFuncW<long>(v72);
  return v52;
}

```

## disassembly

```asm
0x18003ea04  mov     rax, rsp
0x18003ea07  mov     [rax+18h], rbx
0x18003ea0b  mov     [rax+20h], r9d
0x18003ea0f  mov     [rax+10h], rdx
0x18003ea13  push    rbp
0x18003ea14  push    rsi
0x18003ea15  push    rdi
0x18003ea16  push    r12
0x18003ea18  push    r13
0x18003ea1a  push    r14
0x18003ea1c  push    r15
0x18003ea1e  lea     rbp, [rax-58h]
0x18003ea22  sub     rsp, 120h
0x18003ea29  mov     r13, r8
0x18003ea2c  mov     r14, rdx
0x18003ea2f  mov     r12, rcx
0x18003ea32  xor     ebx, ebx
0x18003ea34  mov     dword ptr [rsp+150h+var_110], ebx
0x18003ea38  mov     [rbp+50h+arg_0], ebx
0x18003ea3b  lea     r15, aIdentitystorag; "IdentityStorage::WriteCredentialInforma"...
0x18003ea42  mov     [rbp+50h+var_58], r15
0x18003ea46  lea     rax, [rbp+50h+arg_0]
0x18003ea4a  mov     [rbp+50h+var_50], rax
0x18003ea4e  mov     [rbp+50h+var_48], rbx
0x18003ea52  mov     [rbp+50h+var_40], rbx
0x18003ea56  xor     r9d, r9d; unsigned int
0x18003ea59  mov     r8d, 156h; char *
0x18003ea5f  mov     rdx, r15; char *
0x18003ea62  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003ea69  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003ea6e  nop
0x18003ea6f  mov     rax, [r12]
0x18003ea73  mov     [rbp+50h+var_B0], rax
0x18003ea77  mov     [rbp+50h+var_C0], rbx
0x18003ea7b  mov     [rsp+150h+var_100], ebx
0x18003ea7f  mov     [rbp+50h+var_C8], rax
0x18003ea83  lea     rcx, [rsp+150h+var_F0]; void *
0x18003ea88  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003ea8d  nop
0x18003ea8e  xorps   xmm0, xmm0
0x18003ea91  movups  [rbp+50h+var_A8], xmm0
0x18003ea95  mov     [rsp+150h+var_E8], rbx
0x18003ea9a  mov     [rsp+150h+var_E0], rbx
0x18003ea9f  mov     [rsp+150h+var_D8], rbx
0x18003eaa4  mov     [rbp+50h+var_D0], ebx
0x18003eaa7  mov     [rbp+50h+var_98], rbx
0x18003eaab  mov     [rbp+50h+var_90], rbx
0x18003eaaf  mov     [rbp+50h+var_88], rbx
0x18003eab3  mov     [rbp+50h+var_80], ebx
0x18003eab6  lea     rcx, [rsp+150h+var_108]; void *
0x18003eabb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003eac0  nop
0x18003eac1  lea     rcx, [rsp+150h+var_F8]; void *
0x18003eac6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003eacb  nop
0x18003eacc  lea     rax, qword_18006F818
0x18003ead3  mov     [rsp+150h+var_130], rax; int *
0x18003ead8  lea     r9d, [rbx+0Bh]; unsigned __int64
0x18003eadc  lea     r8, [rbp+50h+arg_0]; int *
0x18003eae0  mov     rdx, r15; char *
0x18003eae3  lea     rcx, [rbp+50h+var_78]; this
0x18003eae7  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18003eaec  nop
0x18003eaed  mov     edi, ebx
0x18003eaef  mov     rsi, [rbp+50h+arg_30]
0x18003eaf6  cmp     [rsi+8], rbx
0x18003eafa  jbe     loc_18003EC13
0x18003eb00  mov     rdx, rdi
0x18003eb03  mov     rcx, rsi
0x18003eb06  call    ??A?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@QEAAAEAU_ModernIdentityProperty@@_K@Z; ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](unsigned __int64)
0x18003eb0b  mov     rcx, rax
0x18003eb0e  lea     rdx, aPwid; "PWID"
0x18003eb15  call    ??8ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator==(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x18003eb1a  mov     rdx, rdi
0x18003eb1d  mov     rcx, rsi
0x18003eb20  test    al, al
0x18003eb22  jz      short loc_18003EB79
0x18003eb24  call    ??A?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@QEAAAEAU_ModernIdentityProperty@@_K@Z; ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](unsigned __int64)
0x18003eb29  mov     rcx, [rax+8]
0x18003eb2d  cmp     [rcx-10h], ebx
0x18003eb30  jz      loc_18003EC06
0x18003eb36  mov     rdx, rdi
0x18003eb39  mov     rcx, rsi
0x18003eb3c  call    ??A?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@QEAAAEAU_ModernIdentityProperty@@_K@Z; ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](unsigned __int64)
0x18003eb41  mov     r9, [rax+8]; unsigned __int16 *
0x18003eb45  mov     r8, [r14]; unsigned __int16 *
0x18003eb48  mov     rdx, [r13+0]; unsigned __int16 *
0x18003eb4c  mov     rcx, r12; this
0x18003eb4f  call    ?WritePairwiseId@IdentityStorage@@AEAAJPEBG00@Z; IdentityStorage::WritePairwiseId(ushort const *,ushort const *,ushort const *)
0x18003eb54  mov     [rbp+50h+arg_0], eax
0x18003eb57  test    eax, eax
0x18003eb59  jns     loc_18003EC06
0x18003eb5f  lea     r8, aHrWritepairwis; "hr = WritePairwiseId(defaultId, applica"...
0x18003eb66  mov     [rsp+150h+var_130], r8
0x18003eb6b  mov     r8d, 16Dh
0x18003eb71  mov     rdx, r15
0x18003eb74  jmp     loc_18003F05F
0x18003eb79  call    ??A?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@QEAAAEAU_ModernIdentityProperty@@_K@Z; ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](unsigned __int64)
0x18003eb7e  mov     rdx, rax
0x18003eb81  lea     rcx, [rbp+50h+var_98]
0x18003eb85  call    ?Add@?$CAtlArray@UIdentityProperty@@V?$CElementTraits@UIdentityProperty@@@ATL@@@ATL@@QEAA_KAEBUIdentityProperty@@@Z; ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::Add(IdentityProperty const &)
0x18003eb8a  mov     rdx, rdi
0x18003eb8d  mov     rcx, rsi
0x18003eb90  call    ??A?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@QEAAAEAU_ModernIdentityProperty@@_K@Z; ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](unsigned __int64)
0x18003eb95  mov     rcx, rax
0x18003eb98  lea     rdx, aAuthmembername; "AuthMembername"
0x18003eb9f  call    ??8ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator==(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x18003eba4  test    al, al
0x18003eba6  jz      short loc_18003EC06
0x18003eba8  mov     rdx, rdi
0x18003ebab  mov     rcx, rsi
0x18003ebae  call    ??A?$CAtlArray@U_ModernIdentityProperty@@V?$CElementTraits@U_ModernIdentityProperty@@@ATL@@@ATL@@QEAAAEAU_ModernIdentityProperty@@_K@Z; ATL::CAtlArray<_ModernIdentityProperty,ATL::CElementTraits<_ModernIdentityProperty>>::operator[](unsigned __int64)
0x18003ebb3  mov     rdx, [rax+8]
0x18003ebb7  lea     rcx, [rdx-18h]
0x18003ebbb  mov     r14, [rsp+150h+var_108]
0x18003ebc0  add     r14, 0FFFFFFFFFFFFFFE8h
0x18003ebc4  cmp     rcx, r14
0x18003ebc7  jz      short loc_18003EC02
0x18003ebc9  cmp     [r14+10h], ebx
0x18003ebcd  jl      short loc_18003EBF4
0x18003ebcf  mov     rax, [r14]
0x18003ebd2  cmp     [rcx], rax
0x18003ebd5  jnz     short loc_18003EBF4
0x18003ebd7  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18003ebdc  mov     rbx, rax
0x18003ebdf  mov     rcx, r14; this
0x18003ebe2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003ebe7  lea     rax, [rbx+18h]
0x18003ebeb  mov     [rsp+150h+var_108], rax
0x18003ebf0  xor     ebx, ebx
0x18003ebf2  jmp     short loc_18003EC02
0x18003ebf4  mov     r8d, [rdx-10h]
0x18003ebf8  lea     rcx, [rsp+150h+var_108]
0x18003ebfd  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003ec02  mov     r14, [rbp+50h+arg_8]
0x18003ec06  inc     rdi
0x18003ec09  cmp     rdi, [rsi+8]
0x18003ec0d  jb      loc_18003EB00
0x18003ec13  mov     r15b, [rbp+50h+arg_38]
0x18003ec1a  cmp     r15b, 1
0x18003ec1e  jnz     short loc_18003EC4D
0x18003ec20  mov     rax, [rsp+150h+var_108]
0x18003ec25  cmp     [rax-10h], ebx
0x18003ec28  jnz     short loc_18003EC4D
0x18003ec2a  lea     r9, aMemberNameWasE; "Member name was empty for a secondary a"...
0x18003ec31  mov     r8d, 180h; unsigned int
0x18003ec37  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003ec3e  mov     ecx, 3; unsigned __int8
0x18003ec43  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003ec48  jmp     loc_18003F06E
0x18003ec4d  lea     r8, [rbp+50h+var_98]
0x18003ec51  mov     rdx, [r13+0]
0x18003ec55  mov     rcx, r12
0x18003ec58  call    ?WriteProperties@IdentityStorage@@AEAAJPEBGAEBV?$CAtlArray@UIdentityProperty@@V?$CElementTraits@UIdentityProperty@@@ATL@@@ATL@@@Z; IdentityStorage::WriteProperties(ushort const *,ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>> const &)
0x18003ec5d  mov     [rbp+50h+arg_0], eax
0x18003ec60  test    eax, eax
0x18003ec62  jns     short loc_18003EC76
0x18003ec64  lea     rcx, aHrWritepropert; "hr = WriteProperties(defaultId, userSco"...
0x18003ec6b  mov     r8d, 184h
0x18003ec71  jmp     loc_18003F053
0x18003ec76  mov     rsi, [rbp+50h+arg_28]
0x18003ec7d  mov     rbx, [rsi+8]
0x18003ec81  test    rbx, rbx
0x18003ec84  jnz     short loc_18003EC8D
0x18003ec86  mov     [rsp+150h+var_D8], rbx
0x18003ec8b  jmp     short loc_18003ECCB
0x18003ec8d  mov     rdx, rbx
0x18003ec90  lea     rcx, [rsp+150h+var_E8]
0x18003ec95  call    ?GrowBuffer@?$CAtlArray@U_ModernAppToken@@V?$CElementTraits@U_ModernAppToken@@@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::GrowBuffer(unsigned __int64)
0x18003ec9a  test    al, al
0x18003ec9c  jnz     short loc_18003ECC6
0x18003ec9e  mov     r9d, 8007000Eh
0x18003eca4  mov     [rbp+50h+arg_0], r9d
0x18003eca8  lea     rax, aTemptokenarray; "tempTokenArray.SetCount(tokenArray.GetC"...
0x18003ecaf  mov     [rsp+150h+var_130], rax
0x18003ecb4  mov     r8d, 187h
0x18003ecba  lea     rdx, aIdentitystorag; "IdentityStorage::WriteCredentialInforma"...
0x18003ecc1  jmp     loc_18003F062
0x18003ecc6  call    ?CallConstructors@?$CAtlArray@U_ModernAppToken@@V?$CElementTraits@U_ModernAppToken@@@ATL@@@ATL@@CAXPEAU_ModernAppToken@@_K@Z; ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::CallConstructors(_ModernAppToken *,unsigned __int64)
0x18003eccb  mov     [rsp+150h+var_E0], rbx
0x18003ecd0  mov     dword ptr [rbp+50h+var_A8], ebx
0x18003ecd3  mov     dword ptr [rbp+50h+arg_30], 0
0x18003ecdd  test    ebx, ebx
0x18003ecdf  jz      loc_18003EDBC
0x18003ece5  mov     r15d, dword ptr [rbp+50h+arg_30]
0x18003ecec  mov     edx, r15d
0x18003ecef  mov     rcx, rsi
0x18003ecf2  call    ??A?$CAtlArray@UIdentityToken@@V?$CElementTraits@UIdentityToken@@@ATL@@@ATL@@QEBAAEBUIdentityToken@@_K@Z; ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](unsigned __int64)
0x18003ecf7  mov     rbx, [rax]
0x18003ecfa  mov     edx, r15d
0x18003ecfd  lea     rcx, [rsp+150h+var_E8]
0x18003ed02  call    ??A?$CAtlArray@U_ModernAppToken@@V?$CElementTraits@U_ModernAppToken@@@ATL@@@ATL@@QEAAAEAU_ModernAppToken@@_K@Z; ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::operator[](unsigned __int64)
0x18003ed07  mov     [rax], rbx
0x18003ed0a  mov     edx, r15d
0x18003ed0d  mov     rcx, rsi
0x18003ed10  call    ??A?$CAtlArray@UIdentityToken@@V?$CElementTraits@UIdentityToken@@@ATL@@@ATL@@QEBAAEBUIdentityToken@@_K@Z; ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](unsigned __int64)
0x18003ed15  mov     rbx, [rax+8]
0x18003ed19  mov     edx, r15d
0x18003ed1c  lea     rcx, [rsp+150h+var_E8]
0x18003ed21  call    ??A?$CAtlArray@U_ModernAppToken@@V?$CElementTraits@U_ModernAppToken@@@ATL@@@ATL@@QEAAAEAU_ModernAppToken@@_K@Z; ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::operator[](unsigned __int64)
0x18003ed26  mov     [rax+8], rbx
0x18003ed2a  mov     edx, r15d
0x18003ed2d  mov     rcx, rsi
0x18003ed30  call    ??A?$CAtlArray@UIdentityToken@@V?$CElementTraits@UIdentityToken@@@ATL@@@ATL@@QEBAAEBUIdentityToken@@_K@Z; ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](unsigned __int64)
0x18003ed35  mov     ebx, [rax+10h]
0x18003ed38  mov     edx, r15d
0x18003ed3b  lea     rcx, [rsp+150h+var_E8]
0x18003ed40  call    ??A?$CAtlArray@U_ModernAppToken@@V?$CElementTraits@U_ModernAppToken@@@ATL@@@ATL@@QEAAAEAU_ModernAppToken@@_K@Z; ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::operator[](unsigned __int64)
0x18003ed45  mov     [rax+10h], ebx
0x18003ed48  mov     edx, r15d
0x18003ed4b  mov     rcx, rsi
0x18003ed4e  call    ??A?$CAtlArray@UIdentityToken@@V?$CElementTraits@UIdentityToken@@@ATL@@@ATL@@QEBAAEBUIdentityToken@@_K@Z; ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](unsigned __int64)
0x18003ed53  mov     rbx, [rax+18h]
0x18003ed57  mov     edx, r15d
0x18003ed5a  lea     rcx, [rsp+150h+var_E8]
0x18003ed5f  call    ??A?$CAtlArray@U_ModernAppToken@@V?$CElementTraits@U_ModernAppToken@@@ATL@@@ATL@@QEAAAEAU_ModernAppToken@@_K@Z; ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::operator[](unsigned __int64)
0x18003ed64  mov     [rax+18h], rbx
0x18003ed68  mov     edx, r15d
0x18003ed6b  mov     rcx, rsi
0x18003ed6e  call    ??A?$CAtlArray@UIdentityToken@@V?$CElementTraits@UIdentityToken@@@ATL@@@ATL@@QEBAAEBUIdentityToken@@_K@Z; ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](unsigned __int64)
0x18003ed73  mov     rbx, [rax+20h]
0x18003ed77  mov     edx, r15d
0x18003ed7a  lea     rcx, [rsp+150h+var_E8]
0x18003ed7f  call    ??A?$CAtlArray@U_ModernAppToken@@V?$CElementTraits@U_ModernAppToken@@@ATL@@@ATL@@QEAAAEAU_ModernAppToken@@_K@Z; ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::operator[](unsigned __int64)
0x18003ed84  mov     [rax+20h], rbx
0x18003ed88  mov     edx, r15d
0x18003ed8b  mov     rcx, rsi
0x18003ed8e  call    ??A?$CAtlArray@UIdentityToken@@V?$CElementTraits@UIdentityToken@@@ATL@@@ATL@@QEBAAEBUIdentityToken@@_K@Z; ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](unsigned __int64)
0x18003ed93  mov     rbx, [rax+28h]
0x18003ed97  mov     edx, r15d
0x18003ed9a  lea     rcx, [rsp+150h+var_E8]
0x18003ed9f  call    ??A?$CAtlArray@U_ModernAppToken@@V?$CElementTraits@U_ModernAppToken@@@ATL@@@ATL@@QEAAAEAU_ModernAppToken@@_K@Z; ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::operator[](unsigned __int64)
0x18003eda4  mov     [rax+28h], rbx
0x18003eda8  inc     r15d
0x18003edab  cmp     r15d, dword ptr [rbp+50h+var_A8]
0x18003edaf  jb      loc_18003ECEC
0x18003edb5  mov     r15b, [rbp+50h+arg_38]
0x18003edbc  mov     rax, [rsp+150h+var_E8]
0x18003edc1  mov     qword ptr [rbp+50h+var_A8+8], rax
0x18003edc5  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\IdentityCRL\\Immer"...
0x18003edcc  lea     rdx, [rbp+50h+var_B8]
0x18003edd0  mov     rcx, r12
0x18003edd3  call    ?GetEnvironmentSpecificRegistryKey@IdentityStorage@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; IdentityStorage::GetEnvironmentSpecificRegistryKey(ushort const *)
0x18003edd8  nop
0x18003edd9  mov     r8, r14
0x18003eddc  mov     rdx, rax
0x18003eddf  lea     rcx, [rbp+50h+arg_30]
0x18003ede6  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003edeb  nop
0x18003edec  mov     rdx, [rax]
0x18003edef  lea     rcx, [rdx-18h]
0x18003edf3  mov     rbx, [rsp+150h+var_F0]
0x18003edf8  lea     rdi, [rbx-18h]
0x18003edfc  cmp     rcx, rdi
0x18003edff  jz      short loc_18003EE3D
0x18003ee01  cmp     dword ptr [rdi+10h], 0
0x18003ee05  jl      short loc_18003EE2A
0x18003ee07  mov     rax, [rdi]
0x18003ee0a  cmp     [rcx], rax
0x18003ee0d  jnz     short loc_18003EE2A
0x18003ee0f  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18003ee14  mov     rbx, rax
0x18003ee17  mov     rcx, rdi; this
0x18003ee1a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003ee1f  add     rbx, 18h
0x18003ee23  mov     [rsp+150h+var_F0], rbx
0x18003ee28  jmp     short loc_18003EE3D
0x18003ee2a  mov     r8d, [rdx-10h]
0x18003ee2e  lea     rcx, [rsp+150h+var_F0]
0x18003ee33  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003ee38  mov     rbx, [rsp+150h+var_F0]
0x18003ee3d  lea     rcx, [rbp+50h+arg_30]; void *
0x18003ee44  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003ee49  nop
0x18003ee4a  lea     rcx, [rbp+50h+var_B8]; void *
0x18003ee4e  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003ee53  lea     rax, [rsp+150h+var_100]
0x18003ee58  mov     [rsp+150h+var_130], rax
0x18003ee5d  lea     r9, [rbp+50h+var_C0]
0x18003ee61  lea     rdx, [rbp+50h+var_A8]
0x18003ee65  lea     rcx, [rbp+50h+var_B0]
0x18003ee69  call    ??$SerializeObjectWithVersion@VModernAppTokenBagSerializer@@U_ModernAppTokenBag@@@@YAJAEAVModernAppTokenBagSerializer@@AEAU_ModernAppTokenBag@@KPEAPEAEPEAK@Z; SerializeObjectWithVersion<ModernAppTokenBagSerializer,_ModernAppTokenBag>(ModernAppTokenBagSerializer &,_ModernAppTokenBag &,ulong,uchar * *,ulong *)
0x18003ee6e  mov     [rbp+50h+arg_0], eax
0x18003ee71  test    eax, eax
0x18003ee73  jns     short loc_18003EE87
0x18003ee75  lea     rcx, aHrSerializeobj_0; "hr = SerializeObjectWithVersion(tokenba"...
0x18003ee7c  mov     r8d, 19Bh
0x18003ee82  jmp     loc_18003F053
0x18003ee87  cmp     r15b, 1
0x18003ee8b  jnz     short loc_18003EEC6
0x18003ee8d  lea     r8, asc_18006DFA8; "|"
0x18003ee94  mov     rdx, r13
0x18003ee97  lea     rcx, [rbp+50h+var_B8]
0x18003ee9b  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x18003eea0  nop
0x18003eea1  mov     dword ptr [rsp+150h+var_110], 1
0x18003eea9  lea     r8, [rsp+150h+var_108]
0x18003eeae  mov     rdx, rax
0x18003eeb1  lea     rcx, [rbp+50h+var_B0]
0x18003eeb5  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
  ... truncated ...
```
