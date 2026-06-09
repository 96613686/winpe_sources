# MicrodomImplementation::CMicrodom::Initialize(MicrodomImplementation::MdCreateParams const &)

- ea: `0x18004c278`
- end: `0x18004c7c2`
- name: `?Initialize@CMicrodom@MicrodomImplementation@@QEAAJAEBUMdCreateParams@2@@Z`
- size: `1354`
- prototype: `__int64 __fastcall(MicrodomImplementation::CMicrodom *__hidden this, const struct MicrodomImplementation::MdCreateParams *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050e28`

## callees

- `0x180037054`
- `0x1800370f4`
- `0x180037488`
- `0x18004c278`
- `0x18004eef0`
- `0x18004f764`
- `0x1800501a4`
- `0x1800504a4`
- `0x180050834`
- `0x1800607b0`
- `0x180060e70`

## string_xrefs

- `0x18004c3db`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004c42b`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004c459`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004c484`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004c4b2`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004c4e0`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004c56f`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004c5bd`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004c5f1`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004c75d`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004c784`: `m_PropertyCache.Allocate(m_LayoutCache.TotalObjectCount())`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom::Initialize(
        MicrodomImplementation::CMicrodom *this,
        const struct MicrodomImplementation::MdCreateParams *a2)
{
  __int64 *v3; // rcx
  __int64 v5; // rax
  int v6; // esi
  void (__fastcall ***v7)(_QWORD); // rdx
  __int64 result; // rax
  _QWORD *v9; // rdx
  struct Windows::Rtl::CRtlTrackTypeDescription *v10; // rcx
  unsigned __int64 v11; // rdx
  const char *v12; // rax
  _DWORD *v13; // rcx
  __int64 v14; // rax
  const struct _MICRODOM_STRINGPOOL_HEADER *v15; // r8
  const struct _MICRODOM_STRINGPOOL_HEADER *v16; // rdx
  _DWORD *v17; // rsi
  _DWORD *v18; // rdi
  const struct _MICRODOM_LOCATION_HEADER *v19; // r14
  _DWORD *v20; // r15
  _DWORD *v21; // rax
  const char *v22; // rax
  __int64 (__fastcall *v23)(); // rax
  __int64 v24; // rdx
  const char *v25; // [rsp+30h] [rbp-30h] BYREF
  const char *v26; // [rsp+38h] [rbp-28h]
  int v27; // [rsp+40h] [rbp-20h]
  const char *v28; // [rsp+48h] [rbp-18h]
  void (__fastcall ***v29)(_QWORD); // [rsp+50h] [rbp-10h] BYREF

  v3 = (__int64 *)*((_QWORD *)a2 + 3);
  LODWORD(v29) = 0;
  if ( !v3 )
  {
    v9 = (_QWORD *)((char *)this + 496);
    if ( *((_BYTE *)a2 + 48) )
    {
      *v9 = *(_QWORD *)a2;
      *((_QWORD *)this + 63) = *((_QWORD *)a2 + 1);
      *((_QWORD *)this + 64) = *((_QWORD *)a2 + 2);
    }
    else
    {
      result = RtlDuplicateLBlob(a2, v9);
      if ( (int)result < 0 )
        return result;
      v10 = Windows::Rtl::g_pTrackTypeDescription;
      *((_BYTE *)this + 552) = 1;
      if ( v10 )
        (*(void (__fastcall **)(struct Windows::Rtl::CRtlTrackTypeDescription *, const char *, __int64, _QWORD, char))(*(_QWORD *)v10 + 16LL))(
          v10,
          "CMicrodom_Blob",
          1,
          *((unsigned int *)this + 124),
          1);
    }
LABEL_18:
    v11 = *((_QWORD *)this + 62);
    if ( v11 < 0x18 )
    {
      v27 = 2440;
      v25 = "onecore\\base\\xml\\udom_microdom.cpp";
      v26 = "MicrodomImplementation::CMicrodom::Initialize";
      v12 = "m_MicrodomDataBlob.Length >= sizeof(MICRODOM_HEADER)";
LABEL_20:
      v28 = v12;
      RtlReportErrorOrigination(&v25, v11, 3221225485LL);
      return 3221225485LL;
    }
    v13 = (_DWORD *)*((_QWORD *)this + 64);
    v14 = (unsigned int)v13[1];
    if ( v14 != v11 )
    {
      v27 = 2443;
      v25 = "onecore\\base\\xml\\udom_microdom.cpp";
      v26 = "MicrodomImplementation::CMicrodom::Initialize";
      v12 = "pHeader->ulTotalSize == m_MicrodomDataBlob.Length";
      goto LABEL_20;
    }
    if ( *v13 != 1682465869 )
    {
      v27 = 2444;
      v25 = "onecore\\base\\xml\\udom_microdom.cpp";
      v26 = "MicrodomImplementation::CMicrodom::Initialize";
      v12 = "pHeader->ulSignature == ('dHdM')";
      goto LABEL_20;
    }
    if ( v13[3] >= (unsigned int)v14 )
    {
      v27 = 2445;
      v25 = "onecore\\base\\xml\\udom_microdom.cpp";
      v26 = "MicrodomImplementation::CMicrodom::Initialize";
      v12 = "pHeader->ulOffsetToDomLayout < pHeader->ulTotalSize";
      goto LABEL_20;
    }
    if ( v13[2] >= (unsigned int)v14 )
    {
      v27 = 2446;
      v25 = "onecore\\base\\xml\\udom_microdom.cpp";
      v26 = "MicrodomImplementation::CMicrodom::Initialize";
      v12 = "pHeader->ulOffsetToStringPool < pHeader->ulTotalSize";
      goto LABEL_20;
    }
    if ( v13[4] >= (unsigned int)v14 )
    {
      v27 = 2447;
      v25 = "onecore\\base\\xml\\udom_microdom.cpp";
      v26 = "MicrodomImplementation::CMicrodom::Initialize";
      v12 = "pHeader->ulOffsetToPositionData < pHeader->ulTotalSize";
      goto LABEL_20;
    }
    *((_QWORD *)this + 68) = v13;
    v15 = 0;
    v16 = 0;
    if ( v13[2] )
    {
      v15 = (const struct _MICRODOM_STRINGPOOL_HEADER *)((char *)v13 + (unsigned int)v13[2]);
      v16 = v15;
    }
    v17 = 0;
    v18 = 0;
    if ( v13[3] )
    {
      v17 = (_DWORD *)((char *)v13 + (unsigned int)v13[3]);
      v18 = v17;
    }
    v19 = 0;
    if ( v13[4] )
      v19 = (const struct _MICRODOM_LOCATION_HEADER *)((char *)v13 + (unsigned int)v13[4]);
    v20 = 0;
    v21 = 0;
    if ( v13[5] )
    {
      v20 = (_DWORD *)((char *)v13 + (unsigned int)v13[5]);
      v21 = v20;
    }
    if ( v16 && *(_DWORD *)v15 != 1884513357 )
    {
      v27 = 2463;
      v25 = "onecore\\base\\xml\\udom_microdom.cpp";
      v26 = "MicrodomImplementation::CMicrodom::Initialize";
      v22 = "pStringPool->Signature == ('pSdM')";
LABEL_42:
      v28 = v22;
      RtlReportErrorOrigination(&v25, v16, 3221225595LL);
      return 3221225595LL;
    }
    if ( v18 && *v17 != 1816421453 )
    {
      v27 = 2466;
      v25 = "onecore\\base\\xml\\udom_microdom.cpp";
      v26 = "MicrodomImplementation::CMicrodom::Initialize";
      v22 = "pDomLayout->ulSignature == ('lDdM')";
      goto LABEL_42;
    }
    if ( v21 && *v20 != 1950639181 )
    {
      v27 = 2469;
      v25 = "onecore\\base\\xml\\udom_microdom.cpp";
      v26 = "MicrodomImplementation::CMicrodom::Initialize";
      v22 = "pDoctype->ulSignature == ('tDdM')";
      goto LABEL_42;
    }
    result = MicrodomImplementation::CStringpoolCache::AttachToStringPool(
               (MicrodomImplementation::CMicrodom *)((char *)this + 32),
               v15);
    if ( (int)result < 0 )
      return result;
    LODWORD(v29) = 0;
    *((_QWORD *)this + 12) = v17;
    *((_QWORD *)this + 10) = v18 + 5;
    switch ( v17[1] & 3 )
    {
      case 1:
        *((_DWORD *)this + 22) = 1;
        v23 = TypeToTypeIndexer<unsigned char>;
        break;
      case 2:
        *((_DWORD *)this + 22) = 2;
        v23 = TypeToTypeIndexer<unsigned short>;
        break;
      case 3:
        *((_DWORD *)this + 22) = 4;
        v23 = TypeToTypeIndexer<unsigned long>;
        break;
      default:
        goto LABEL_57;
    }
    *((_QWORD *)this + 13) = v23;
LABEL_57:
    result = *(unsigned int *)BUCL::CVector<MicrodomImplementation::CDomLayoutCache::CCachedInformation,BUCL::Rtl::CCallDisposition>::Resize(
                                (char *)this + 48,
                                &v29,
                                (unsigned int)v17[2]);
    if ( (int)result >= 0 )
      result = 0;
    else
      LODWORD(v29) = result;
    if ( (int)result >= 0 )
    {
      if ( *((MicrodomImplementation::CMicrodom **)this + 15) == (MicrodomImplementation::CMicrodom *)((char *)this + 160) )
      {
        BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(
          &v29,
          *((_QWORD *)this + 17),
          5,
          (char *)this + 152);
        result = 0;
        if ( (int)v29 < 0 )
          result = (unsigned int)v29;
        if ( (int)result >= 0 )
        {
          *((_QWORD *)this + 56) = v20;
          *((_QWORD *)this + 53) = v20 + 2;
          *((_QWORD *)this + 54) = v20 + 2;
          result = *(unsigned int *)BUCL::CVector<_MICRODOM_DOCTYPE_NODE_HEADER *,BUCL::Rtl::CCallDisposition>::Reserve(
                                      (char *)this + 392,
                                      &v29,
                                      (unsigned int)v20[1]);
          if ( (int)result >= 0 )
            result = 0;
          if ( (int)result >= 0 )
          {
            if ( !v19
              || (result = MicrodomImplementation::CDomPositionCache::AttachToPositionList(
                             (MicrodomImplementation::CMicrodom *)((char *)this + 456),
                             v19),
                  (int)result >= 0) )
            {
              if ( Windows::AutoVectorBase<Windows::VectorTraits<MicrodomImplementation::CMicrodom::CPropertyCacheEntry>,Windows::Auto<Windows::Vector<MicrodomImplementation::CMicrodom::CPropertyCacheEntry>>>::Allocate(
                     (char *)this + 600,
                     *(unsigned int *)(*((_QWORD *)this + 12) + 8LL)) )
              {
                return 0;
              }
              else
              {
                v27 = 2485;
                v25 = "onecore\\base\\xml\\udom_microdom.cpp";
                v26 = "MicrodomImplementation::CMicrodom::Initialize";
                v28 = "m_PropertyCache.Allocate(m_LayoutCache.TotalObjectCount())";
                RtlReportErrorOrigination(&v25, v24, 3221225495LL);
                return 3221225495LL;
              }
            }
          }
        }
      }
      else
      {
        __debugbreak();
        return 3221225701LL;
      }
    }
    return result;
  }
  v5 = *v3;
  v29 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, GUID *, void (__fastcall ****)(_QWORD)))(v5 + 8))(
         v3,
         &GUID_31257d4b_3df7_46f9_86c5_1c76711e334e,
         &v29);
  if ( v6 < 0 )
  {
    v7 = v29;
  }
  else
  {
    if ( !v29 )
      return (unsigned int)-1073741127;
    v7 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 70);
    *((_QWORD *)this + 70) = v29;
  }
  if ( v7 )
  {
    v29 = 0;
    (**v7)(v7);
  }
  if ( v6 < 0 )
    return (unsigned int)v6;
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, char *))(**((_QWORD **)this + 70) + 16LL))(
             *((_QWORD *)this + 70),
             *((_QWORD *)a2 + 4),
             *((_QWORD *)a2 + 5),
             (char *)this + 568,
             (char *)this + 496);
  if ( (int)result >= 0 )
    goto LABEL_18;
  return result;
}

```

## disassembly

```asm
0x18004c278  mov     [rsp-28h+arg_10], rbx
0x18004c27d  mov     [rsp-28h+arg_18], rsi
0x18004c282  push    rbp
0x18004c283  push    rdi
0x18004c284  push    r12
0x18004c286  push    r14
0x18004c288  push    r15
0x18004c28a  mov     rbp, rsp
0x18004c28d  sub     rsp, 60h
0x18004c291  mov     rax, cs:__security_cookie
0x18004c298  xor     rax, rsp
0x18004c29b  mov     [rbp+var_8], rax
0x18004c29f  xor     r12d, r12d
0x18004c2a2  mov     rbx, rcx
0x18004c2a5  mov     rcx, [rdx+18h]
0x18004c2a9  mov     rdi, rdx
0x18004c2ac  mov     dword ptr [rbp+var_10], r12d
0x18004c2b0  test    rcx, rcx
0x18004c2b3  jz      loc_18004C35A
0x18004c2b9  mov     rax, [rcx]
0x18004c2bc  lea     r8, [rbp+var_10]
0x18004c2c0  lea     rdx, _GUID_31257d4b_3df7_46f9_86c5_1c76711e334e
0x18004c2c7  mov     [rbp+var_10], r12
0x18004c2cb  mov     rax, [rax+8]
0x18004c2cf  call    cs:__guard_dispatch_icall_fptr
0x18004c2d5  mov     esi, eax
0x18004c2d7  test    eax, eax
0x18004c2d9  js      short loc_18004C2FB
0x18004c2db  mov     rcx, [rbp+var_10]
0x18004c2df  test    rcx, rcx
0x18004c2e2  jnz     short loc_18004C2EB
0x18004c2e4  mov     esi, 0C00002B9h
0x18004c2e9  jmp     short loc_18004C31B
0x18004c2eb  mov     rdx, [rbx+230h]
0x18004c2f2  mov     [rbx+230h], rcx
0x18004c2f9  jmp     short loc_18004C2FF
0x18004c2fb  mov     rdx, [rbp+var_10]
0x18004c2ff  test    rdx, rdx
0x18004c302  jz      short loc_18004C317
0x18004c304  mov     [rbp+var_10], r12
0x18004c308  mov     rcx, rdx
0x18004c30b  mov     rax, [rdx]
0x18004c30e  mov     rax, [rax]
0x18004c311  call    cs:__guard_dispatch_icall_fptr
0x18004c317  test    esi, esi
0x18004c319  jns     short loc_18004C322
0x18004c31b  mov     eax, esi
0x18004c31d  jmp     loc_18004C79D
0x18004c322  mov     rcx, [rbx+230h]
0x18004c329  lea     r8, [rbx+1F0h]
0x18004c330  mov     rdx, [rdi+20h]
0x18004c334  lea     r9, [rbx+238h]
0x18004c33b  mov     [rsp+60h+var_40], r8
0x18004c340  mov     r8, [rdi+28h]
0x18004c344  mov     rax, [rcx]
0x18004c347  mov     rax, [rax+10h]
0x18004c34b  call    cs:__guard_dispatch_icall_fptr
0x18004c351  test    eax, eax
0x18004c353  jns     short loc_18004C3CE
0x18004c355  jmp     loc_18004C79D
0x18004c35a  lea     rdx, [rbx+1F0h]
0x18004c361  cmp     [rdi+30h], r12b
0x18004c365  jz      short loc_18004C385
0x18004c367  mov     rax, [rdi]
0x18004c36a  mov     [rdx], rax
0x18004c36d  mov     rax, [rdi+8]
0x18004c371  mov     [rbx+1F8h], rax
0x18004c378  mov     rax, [rdi+10h]
0x18004c37c  mov     [rbx+200h], rax
0x18004c383  jmp     short loc_18004C3CE
0x18004c385  mov     rcx, rdi
0x18004c388  call    RtlDuplicateLBlob
0x18004c38d  test    eax, eax
0x18004c38f  js      loc_18004C79D
0x18004c395  mov     rcx, cs:?g_pTrackTypeDescription@Rtl@Windows@@3PEAVCRtlTrackTypeDescription@12@EA; Windows::Rtl::CRtlTrackTypeDescription * Windows::Rtl::g_pTrackTypeDescription
0x18004c39c  mov     byte ptr [rbx+228h], 1
0x18004c3a3  test    rcx, rcx
0x18004c3a6  jz      short loc_18004C3CE
0x18004c3a8  mov     rax, [rcx]
0x18004c3ab  lea     rdx, aCmicrodomBlob; "CMicrodom_Blob"
0x18004c3b2  mov     r9d, [rbx+1F0h]
0x18004c3b9  mov     r8d, 1
0x18004c3bf  mov     byte ptr [rsp+60h+var_40], 1
0x18004c3c4  mov     rax, [rax+10h]
0x18004c3c8  call    cs:__guard_dispatch_icall_fptr
0x18004c3ce  mov     rdx, [rbx+1F0h]
0x18004c3d5  cmp     rdx, 18h
0x18004c3d9  jnb     short loc_18004C41C
0x18004c3db  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004c3e2  mov     [rbp+var_20], 988h
0x18004c3e9  mov     [rbp+var_30], rax
0x18004c3ed  lea     rax, aMicrodomimplem_19; "MicrodomImplementation::CMicrodom::Init"...
0x18004c3f4  mov     [rbp+var_28], rax
0x18004c3f8  lea     rax, aMMicrodomdatab; "m_MicrodomDataBlob.Length >= sizeof(MIC"...
0x18004c3ff  mov     r8d, 0C000000Dh
0x18004c405  mov     [rbp+var_18], rax
0x18004c409  lea     rcx, [rbp+var_30]
0x18004c40d  call    RtlReportErrorOrigination
0x18004c412  mov     eax, 0C000000Dh
0x18004c417  jmp     loc_18004C79D
0x18004c41c  mov     rcx, [rbx+200h]
0x18004c423  mov     eax, [rcx+4]
0x18004c426  cmp     rax, rdx
0x18004c429  jz      short loc_18004C451
0x18004c42b  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004c432  mov     [rbp+var_20], 98Bh
0x18004c439  mov     [rbp+var_30], rax
0x18004c43d  lea     rax, aMicrodomimplem_19; "MicrodomImplementation::CMicrodom::Init"...
0x18004c444  mov     [rbp+var_28], rax
0x18004c448  lea     rax, aPheaderUltotal; "pHeader->ulTotalSize == m_MicrodomDataB"...
0x18004c44f  jmp     short loc_18004C3FF
0x18004c451  cmp     dword ptr [rcx], 6448644Dh
0x18004c457  jz      short loc_18004C47F
0x18004c459  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004c460  mov     [rbp+var_20], 98Ch
0x18004c467  mov     [rbp+var_30], rax
0x18004c46b  lea     rax, aMicrodomimplem_19; "MicrodomImplementation::CMicrodom::Init"...
0x18004c472  mov     [rbp+var_28], rax
0x18004c476  lea     rax, aPheaderUlsigna; "pHeader->ulSignature == ('dHdM')"
0x18004c47d  jmp     short loc_18004C3FF
0x18004c47f  cmp     [rcx+0Ch], eax
0x18004c482  jb      short loc_18004C4AD
0x18004c484  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004c48b  mov     [rbp+var_20], 98Dh
0x18004c492  mov     [rbp+var_30], rax
0x18004c496  lea     rax, aMicrodomimplem_19; "MicrodomImplementation::CMicrodom::Init"...
0x18004c49d  mov     [rbp+var_28], rax
0x18004c4a1  lea     rax, aPheaderUloffse; "pHeader->ulOffsetToDomLayout < pHeader-"...
0x18004c4a8  jmp     loc_18004C3FF
0x18004c4ad  cmp     [rcx+8], eax
0x18004c4b0  jb      short loc_18004C4DB
0x18004c4b2  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004c4b9  mov     [rbp+var_20], 98Eh
0x18004c4c0  mov     [rbp+var_30], rax
0x18004c4c4  lea     rax, aMicrodomimplem_19; "MicrodomImplementation::CMicrodom::Init"...
0x18004c4cb  mov     [rbp+var_28], rax
0x18004c4cf  lea     rax, aPheaderUloffse_1; "pHeader->ulOffsetToStringPool < pHeader"...
0x18004c4d6  jmp     loc_18004C3FF
0x18004c4db  cmp     [rcx+10h], eax
0x18004c4de  jb      short loc_18004C509
0x18004c4e0  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004c4e7  mov     [rbp+var_20], 98Fh
0x18004c4ee  mov     [rbp+var_30], rax
0x18004c4f2  lea     rax, aMicrodomimplem_19; "MicrodomImplementation::CMicrodom::Init"...
0x18004c4f9  mov     [rbp+var_28], rax
0x18004c4fd  lea     rax, aPheaderUloffse_0; "pHeader->ulOffsetToPositionData < pHead"...
0x18004c504  jmp     loc_18004C3FF
0x18004c509  mov     [rbx+220h], rcx
0x18004c510  mov     r8, r12
0x18004c513  mov     rdx, r12
0x18004c516  cmp     [rcx+8], r12d
0x18004c51a  jz      short loc_18004C526
0x18004c51c  mov     r8d, [rcx+8]
0x18004c520  add     r8, rcx
0x18004c523  mov     rdx, r8
0x18004c526  mov     rsi, r12
0x18004c529  mov     rdi, r12
0x18004c52c  cmp     [rcx+0Ch], r12d
0x18004c530  jz      short loc_18004C53B
0x18004c532  mov     esi, [rcx+0Ch]
0x18004c535  add     rsi, rcx
0x18004c538  mov     rdi, rsi
0x18004c53b  mov     r14, r12
0x18004c53e  cmp     [rcx+10h], r12d
0x18004c542  jz      short loc_18004C54B
0x18004c544  mov     r14d, [rcx+10h]
0x18004c548  add     r14, rcx
0x18004c54b  mov     r15, r12
0x18004c54e  mov     rax, r12
0x18004c551  cmp     [rcx+14h], r12d
0x18004c555  jz      short loc_18004C561
0x18004c557  mov     r15d, [rcx+14h]
0x18004c55b  add     r15, rcx
0x18004c55e  mov     rax, r15
0x18004c561  test    rdx, rdx
0x18004c564  jz      short loc_18004C5B0
0x18004c566  cmp     dword ptr [r8], 7053644Dh
0x18004c56d  jz      short loc_18004C5B0
0x18004c56f  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004c576  mov     [rbp+var_20], 99Fh
0x18004c57d  mov     [rbp+var_30], rax
0x18004c581  lea     rax, aMicrodomimplem_19; "MicrodomImplementation::CMicrodom::Init"...
0x18004c588  mov     [rbp+var_28], rax
0x18004c58c  lea     rax, aPstringpoolSig; "pStringPool->Signature == ('pSdM')"
0x18004c593  mov     r8d, 0C000007Bh
0x18004c599  mov     [rbp+var_18], rax
0x18004c59d  lea     rcx, [rbp+var_30]
0x18004c5a1  call    RtlReportErrorOrigination
0x18004c5a6  mov     eax, 0C000007Bh
0x18004c5ab  jmp     loc_18004C79D
0x18004c5b0  test    rdi, rdi
0x18004c5b3  jz      short loc_18004C5E3
0x18004c5b5  cmp     dword ptr [rsi], 6C44644Dh
0x18004c5bb  jz      short loc_18004C5E3
0x18004c5bd  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004c5c4  mov     [rbp+var_20], 9A2h
0x18004c5cb  mov     [rbp+var_30], rax
0x18004c5cf  lea     rax, aMicrodomimplem_19; "MicrodomImplementation::CMicrodom::Init"...
0x18004c5d6  mov     [rbp+var_28], rax
0x18004c5da  lea     rax, aPdomlayoutUlsi; "pDomLayout->ulSignature == ('lDdM')"
0x18004c5e1  jmp     short loc_18004C593
0x18004c5e3  test    rax, rax
0x18004c5e6  jz      short loc_18004C61A
0x18004c5e8  cmp     dword ptr [r15], 7444644Dh
0x18004c5ef  jz      short loc_18004C61A
0x18004c5f1  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004c5f8  mov     [rbp+var_20], 9A5h
0x18004c5ff  mov     [rbp+var_30], rax
0x18004c603  lea     rax, aMicrodomimplem_19; "MicrodomImplementation::CMicrodom::Init"...
0x18004c60a  mov     [rbp+var_28], rax
0x18004c60e  lea     rax, aPdoctypeUlsign; "pDoctype->ulSignature == ('tDdM')"
0x18004c615  jmp     loc_18004C593
0x18004c61a  lea     rcx, [rbx+20h]; this
0x18004c61e  mov     rdx, r8; struct _MICRODOM_STRINGPOOL_HEADER *
0x18004c621  call    ?AttachToStringPool@CStringpoolCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_STRINGPOOL_HEADER@@@Z; MicrodomImplementation::CStringpoolCache::AttachToStringPool(_MICRODOM_STRINGPOOL_HEADER const *)
0x18004c626  test    eax, eax
0x18004c628  js      loc_18004C79D
0x18004c62e  lea     rcx, [rbx+30h]
0x18004c632  mov     dword ptr [rbp+var_10], r12d
0x18004c636  lea     rax, [rdi+14h]
0x18004c63a  mov     [rcx+30h], rsi
0x18004c63e  mov     [rcx+20h], rax
0x18004c642  mov     eax, [rsi+4]
0x18004c645  and     eax, 3
0x18004c648  sub     eax, 1
0x18004c64b  jz      short loc_18004C677
0x18004c64d  sub     eax, 1
0x18004c650  jz      short loc_18004C667
0x18004c652  cmp     eax, 1
0x18004c655  jnz     short loc_18004C689
0x18004c657  mov     dword ptr [rcx+28h], 4
0x18004c65e  lea     rax, ??$TypeToTypeIndexer@K@@YAKPEBXK@Z; TypeToTypeIndexer<ulong>(void const *,ulong)
0x18004c665  jmp     short loc_18004C685
0x18004c667  mov     dword ptr [rcx+28h], 2
0x18004c66e  lea     rax, ??$TypeToTypeIndexer@G@@YAKPEBXK@Z; TypeToTypeIndexer<ushort>(void const *,ulong)
0x18004c675  jmp     short loc_18004C685
0x18004c677  mov     dword ptr [rcx+28h], 1
0x18004c67e  lea     rax, ??$TypeToTypeIndexer@E@@YAKPEBXK@Z; TypeToTypeIndexer<uchar>(void const *,ulong)
0x18004c685  mov     [rcx+38h], rax
0x18004c689  mov     r8d, [rsi+8]
0x18004c68d  lea     rdx, [rbp+var_10]
0x18004c691  call    ?Resize@?$CVector@VCCachedInformation@CDomLayoutCache@MicrodomImplementation@@VCCallDisposition@Rtl@BUCL@@@BUCL@@QEAA?AVCCallDisposition@Rtl@2@_K@Z; BUCL::CVector<MicrodomImplementation::CDomLayoutCache::CCachedInformation,BUCL::Rtl::CCallDisposition>::Resize(unsigned __int64)
0x18004c696  mov     eax, [rax]
0x18004c698  test    eax, eax
0x18004c69a  jns     short loc_18004C6A1
0x18004c69c  mov     dword ptr [rbp+var_10], eax
0x18004c69f  jmp     short loc_18004C6A4
0x18004c6a1  mov     eax, r12d
0x18004c6a4  test    eax, eax
0x18004c6a6  js      loc_18004C79D
0x18004c6ac  lea     rax, [rbx+0A0h]
0x18004c6b3  cmp     [rbx+78h], rax
0x18004c6b7  jz      short loc_18004C6C4
0x18004c6b9  int     3; Trap to Debugger
0x18004c6ba  mov     eax, 0C00000E5h
0x18004c6bf  jmp     loc_18004C79D
0x18004c6c4  mov     rdx, [rbx+88h]
0x18004c6cb  lea     r9, [rbx+98h]
0x18004c6d2  mov     r8d, 5
0x18004c6d8  lea     rcx, [rbp+var_10]
0x18004c6dc  call    ??$Multiply@VCCallDisposition@Rtl@BUCL@@_K@Implementation@BUCL@@YA?AVCCallDisposition@Rtl@1@_K0AEA_K@Z; BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x18004c6e1  mov     ecx, dword ptr [rbp+var_10]
0x18004c6e4  mov     eax, r12d
0x18004c6e7  test    ecx, ecx
0x18004c6e9  cmovs   eax, ecx
0x18004c6ec  test    eax, eax
0x18004c6ee  js      loc_18004C79D
0x18004c6f4  lea     rax, [r15+8]
0x18004c6f8  mov     [rbx+1C0h], r15
0x18004c6ff  mov     [rbx+1A8h], rax
0x18004c706  lea     rcx, [rbx+188h]
0x18004c70d  mov     [rbx+1B0h], rax
0x18004c714  lea     rdx, [rbp+var_10]
0x18004c718  mov     r8d, [r15+4]
0x18004c71c  call    ?Reserve@?$CVector@PEAU_MICRODOM_DOCTYPE_NODE_HEADER@@VCCallDisposition@Rtl@BUCL@@@BUCL@@QEAA?AVCCallDisposition@Rtl@2@_K@Z; BUCL::CVector<_MICRODOM_DOCTYPE_NODE_HEADER *,BUCL::Rtl::CCallDisposition>::Reserve(unsigned __int64)
0x18004c721  mov     eax, [rax]
0x18004c723  test    eax, eax
0x18004c725  cmovns  eax, r12d
0x18004c729  test    eax, eax
0x18004c72b  js      short loc_18004C79D
0x18004c72d  test    r14, r14
0x18004c730  jz      short loc_18004C745
0x18004c732  lea     rcx, [rbx+1C8h]; this
0x18004c739  mov     rdx, r14; struct _MICRODOM_LOCATION_HEADER *
0x18004c73c  call    ?AttachToPositionList@CDomPositionCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_LOCATION_HEADER@@@Z; MicrodomImplementation::CDomPositionCache::AttachToPositionList(_MICRODOM_LOCATION_HEADER const *)
0x18004c741  test    eax, eax
0x18004c743  js      short loc_18004C79D
0x18004c745  mov     rax, [rbx+60h]
0x18004c749  lea     rcx, [rbx+258h]
0x18004c750  mov     edx, [rax+8]
0x18004c753  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@VCPropertyCacheEntry@CMicrodom@MicrodomImplementation@@@Windows@@V?$Auto@U?$Vector@VCPropertyCacheEntry@CMicrodom@MicrodomImplementation@@@Windows@@@2@@Windows@@QEAAPEAVCPropertyCacheEntry@CMicrodom@MicrodomImplementation@@_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<MicrodomImplementation::CMicrodom::CPropertyCacheEntry>,Windows::Auto<Windows::Vector<MicrodomImplementation::CMicrodom::CPropertyCacheEntry>>>::Allocate(unsigned __int64)
0x18004c758  test    rax, rax
0x18004c75b  jnz     short loc_18004C79B
0x18004c75d  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004c764  mov     [rbp+var_20], 9B5h
0x18004c76b  mov     [rbp+var_30], rax
0x18004c76f  lea     rcx, [rbp+var_30]
0x18004c773  lea     rax, aMicrodomimplem_19; "MicrodomImplementation::CMicrodom::Init"...
0x18004c77a  mov     r8d, 0C0000017h
0x18004c780  mov     [rbp+var_28], rax
  ... truncated ...
```
