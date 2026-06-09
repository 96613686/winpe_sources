# CASFMMStream::CreateHeaderObject(CASFLonghandObject * *,CASFArchive &)

- ea: `0x180012080`
- end: `0x180012e30`
- name: `?CreateHeaderObject@CASFMMStream@@MEAAJPEAPEAVCASFLonghandObject@@AEAVCASFArchive@@@Z`
- size: `3504`
- prototype: `int(CASFMMStream *__hidden this, struct CASFLonghandObject **, struct CASFArchive *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002660`

## callees

- `0x1800011a0`
- `0x1800015f0`
- `0x180012080`
- `0x180014de8`
- `0x180014ee4`
- `0x180014f40`
- `0x180014ffc`
- `0x1800150a8`
- `0x180015130`
- `0x180015194`
- `0x1800151f8`
- `0x180015254`
- `0x1800152c4`
- `0x180015318`
- `0x180015444`
- `0x180015500`
- `0x180015578`
- `0x180022980`
- `0x180027984`
- `0x1800279b4`
- `0x1800279e8`
- `0x18002a064`
- `0x18002b010`

## pseudocode

```c
int __fastcall CASFMMStream::CreateHeaderObject(
        CASFMMStream *this,
        struct CASFLonghandObject **a2,
        struct CASFArchive *a3)
{
  int result; // eax
  unsigned __int64 v6; // rdi
  CASFMutualExclusionObjectEx *v7; // rax
  CASFStreamPropertiesObject *v8; // rax
  CASFStreamPropertiesObject *v9; // rax
  CASFStreamPropertiesObject *v10; // rax
  CASFStreamPropertiesObject *v11; // rax
  CASFStreamPropertiesObject *v12; // rax
  CASFStreamPropertiesObjectEx *v13; // rax
  CASFContentDescriptionObject *v14; // rax
  struct CASFLonghandObject *v15; // rax
  struct CASFLonghandObject *v16; // rcx
  GUID v17; // xmm0
  CASFIndexObjectEx *v18; // rax
  CASFMediaObjectIndexParametersObjectV1 *v19; // rax
  CASFMediaObjectIndexObjectV1 *v20; // rax
  CASFSMPTEIndexParametersObjectV1 *v21; // rax
  CASFSMPTEIndexObjectV1 *v22; // rax
  GUID v23; // xmm0
  GUID *v24; // rax
  char *v25; // rax
  CASFMutualExclusionObjectEx *v26; // rax
  CASFGroupMutualExclusionObject *v27; // rax
  CASFStreamPrioritizationObject *v28; // rax
  char *v29; // rax
  CASFV1LanguageListObject *v30; // rax
  CASFExtendedStreamPropertiesObject *v31; // rax
  CASFAdvancedContentEncryptionObject *v32; // rax
  GUID v33; // xmm0
  CASFAdvancedContentEncryptionObject *v34; // rax
  GUID v35; // xmm0
  GUID v36; // xmm0
  CASFIndexParametersPlaceholderObject *v37; // rax
  CASFV1MetadataObject *v38; // rax
  CASFV1MetadataLibraryObject *v39; // rax
  int v40; // edi
  __int128 Buf1; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v42[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v43; // [rsp+40h] [rbp-30h]
  unsigned __int64 v44; // [rsp+50h] [rbp-20h]
  __int64 v45; // [rsp+58h] [rbp-18h]
  __int64 v46; // [rsp+60h] [rbp-10h]

  if ( !a2 )
    return -2147024809;
  *a2 = 0;
  v6 = *((_QWORD *)a3 + 1);
  v42[0] = &CASFLonghandObject::`vftable';
  v46 = 1;
  v45 = 0;
  v42[1] = 100;
  result = CASFLonghandObject::Restore((CASFLonghandObject *)v42, a3);
  if ( result >= 0 )
  {
    if ( v6 >= *(_QWORD *)a3 && v6 <= *((_QWORD *)a3 + 2) )
      *((_QWORD *)a3 + 1) = v6;
    if ( v44 > *(_QWORD *)a3
             + (unsigned __int64)(unsigned int)(*((_DWORD *)a3 + 4) - *(_DWORD *)a3)
             - *((_QWORD *)a3 + 1) )
      return -1072887856;
    Buf1 = v43;
    if ( !memcmp_0(&Buf1, &CLSID_CAsfHeaderObjectV0, 0x10u) )
    {
      v7 = (CASFMutualExclusionObjectEx *)operator new(0x40u);
      if ( v7 )
      {
        *((_QWORD *)v7 + 5) = 0;
        *(_QWORD *)v7 = &CASFHeaderObject::`vftable';
        *((_QWORD *)v7 + 6) = 1;
        *((_DWORD *)v7 + 2) = 101;
        *((GUID *)v7 + 1) = CLSID_CAsfHeaderObjectV0;
LABEL_79:
        *a2 = v7;
LABEL_104:
        *((_DWORD *)v7 + 3) = 0;
        goto LABEL_153;
      }
      goto LABEL_105;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfPropertiesObjectV0, 0x10u) )
    {
      v7 = (CASFMutualExclusionObjectEx *)operator new(0x98u);
      if ( v7 )
      {
        *((_QWORD *)v7 + 5) = 0;
        *(_QWORD *)v7 = &CDVRASFPropertiesObject::`vftable';
        *((_QWORD *)v7 + 6) = 1;
        *((_DWORD *)v7 + 2) = 102;
        *((GUID *)v7 + 1) = CLSID_CAsfPropertiesObjectV2;
        goto LABEL_79;
      }
      goto LABEL_105;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfPropertiesObjectV1, 0x10u) )
    {
      v8 = (CASFStreamPropertiesObject *)operator new(0x98u);
      if ( v8 )
      {
        *((_QWORD *)v8 + 5) = 0;
        *(_QWORD *)v8 = &CDVRASFPropertiesObject::`vftable';
        *((_QWORD *)v8 + 6) = 1;
        *((_DWORD *)v8 + 2) = 102;
        *((GUID *)v8 + 1) = CLSID_CAsfPropertiesObjectV2;
        *a2 = v8;
LABEL_27:
        *((_DWORD *)v8 + 3) = 1;
        goto LABEL_153;
      }
      goto LABEL_105;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfPropertiesObjectV2, 0x10u) )
    {
      v9 = (CASFStreamPropertiesObject *)operator new(0x98u);
      if ( !v9 )
        goto LABEL_105;
      *((_QWORD *)v9 + 5) = 0;
      *(_QWORD *)v9 = &CDVRASFPropertiesObject::`vftable';
      *((_QWORD *)v9 + 6) = 1;
      *((_DWORD *)v9 + 2) = 102;
      *((GUID *)v9 + 1) = CLSID_CAsfPropertiesObjectV2;
      *a2 = v9;
LABEL_31:
      *((_DWORD *)v9 + 3) = 2;
      goto LABEL_153;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfStreamPropertiesObjectV0, 0x10u) )
    {
      v10 = (CASFStreamPropertiesObject *)operator new(0x88u);
      if ( !v10 )
        goto LABEL_105;
      v7 = CASFStreamPropertiesObject::CASFStreamPropertiesObject(v10);
LABEL_103:
      *a2 = v7;
      if ( !v7 )
        goto LABEL_153;
      goto LABEL_104;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfStreamPropertiesObjectV1, 0x10u) )
    {
      v11 = (CASFStreamPropertiesObject *)operator new(0x88u);
      if ( v11 )
      {
        v8 = CASFStreamPropertiesObject::CASFStreamPropertiesObject(v11);
        *a2 = v8;
        if ( !v8 )
          goto LABEL_153;
        goto LABEL_27;
      }
LABEL_105:
      *a2 = 0;
      goto LABEL_153;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfStreamPropertiesObjectV2, 0x10u) )
    {
      v12 = (CASFStreamPropertiesObject *)operator new(0x88u);
      if ( !v12 )
        goto LABEL_105;
      v9 = CASFStreamPropertiesObject::CASFStreamPropertiesObject(v12);
      *a2 = v9;
      if ( !v9 )
        goto LABEL_153;
      goto LABEL_31;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfStreamPropertiesObjectEx, 0x10u) )
    {
      v13 = (CASFStreamPropertiesObjectEx *)operator new(0x248u);
      if ( !v13 )
        goto LABEL_105;
      v7 = CASFStreamPropertiesObjectEx::CASFStreamPropertiesObjectEx(v13);
      goto LABEL_103;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfContentDescriptionObjectV0, 0x10u) )
    {
      v14 = (CASFContentDescriptionObject *)operator new(0x70u);
      if ( !v14 )
        goto LABEL_105;
      v7 = CASFContentDescriptionObject::CASFContentDescriptionObject(v14);
      goto LABEL_103;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfDataObjectV0, 0x10u) )
    {
      v7 = (CASFMutualExclusionObjectEx *)operator new(0x58u);
      if ( v7 )
      {
        *((_QWORD *)v7 + 5) = 0;
        *(_QWORD *)v7 = &CDVRASFDataObject::`vftable';
        *((_QWORD *)v7 + 6) = 1;
        *((_DWORD *)v7 + 2) = 114;
        *((GUID *)v7 + 1) = CLSID_CAsfDataObjectV0;
        goto LABEL_79;
      }
      goto LABEL_105;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfIndexObjectV0, 0x10u) || !memcmp_0(&Buf1, &CLSID_CAsfMarkerObjectV0, 0x10u) )
    {
      v15 = (struct CASFLonghandObject *)operator new(0x60u);
      v16 = v15;
      if ( !v15 )
        goto LABEL_105;
      *((_QWORD *)v15 + 5) = 0;
      *((_QWORD *)v15 + 6) = 1;
      *(_QWORD *)v15 = &CASFMarkerObject::`vftable';
      v17 = CLSID_CAsfMarkerObjectV0;
      *((_DWORD *)v15 + 2) = 107;
      *((_QWORD *)v15 + 10) = 0;
      *((_WORD *)v15 + 39) = 0;
      *((_QWORD *)v15 + 11) = 0;
      *((_DWORD *)v15 + 18) = 0;
      goto LABEL_95;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfIndexObjectV2, 0x10u) )
    {
      v7 = (CASFMutualExclusionObjectEx *)operator new(0x60u);
      if ( v7 )
      {
        *((_QWORD *)v7 + 5) = 0;
        *(_QWORD *)v7 = &CASFIndexObject::`vftable';
        *((_QWORD *)v7 + 6) = 1;
        *((_DWORD *)v7 + 2) = 108;
        *((_QWORD *)v7 + 11) = 0;
        *((GUID *)v7 + 1) = CLSID_CAsfIndexObjectV2;
        *((_QWORD *)v7 + 10) = 0;
        goto LABEL_79;
      }
      goto LABEL_105;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfIndexParametersObject, 0x10u) )
    {
      v7 = (CASFMutualExclusionObjectEx *)operator new(0x48u);
      if ( v7 )
      {
        *((_QWORD *)v7 + 5) = 0;
        *(_QWORD *)v7 = &CASFIndexParametersObject::`vftable';
        *((_DWORD *)v7 + 2) = 100;
        *((_QWORD *)v7 + 6) = 1;
        *((_DWORD *)v7 + 14) = 1000;
        *((_WORD *)v7 + 30) = 0;
        *((GUID *)v7 + 1) = CLSID_CAsfIndexParametersObject;
        *((_QWORD *)v7 + 8) = 0;
        goto LABEL_79;
      }
      goto LABEL_105;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfIndexObjectEx, 0x10u) )
    {
      v18 = (CASFIndexObjectEx *)operator new(0x58u);
      if ( !v18 )
        goto LABEL_105;
      v7 = CASFIndexObjectEx::CASFIndexObjectEx(v18);
      goto LABEL_103;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfMediaObjectIndexParametersObject, 0x10u) )
    {
      v19 = (CASFMediaObjectIndexParametersObjectV1 *)operator new(0x48u);
      if ( !v19 )
        goto LABEL_105;
      v7 = CASFMediaObjectIndexParametersObjectV1::CASFMediaObjectIndexParametersObjectV1(v19);
      goto LABEL_103;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfMediaObjectIndexObject, 0x10u) )
    {
      v20 = (CASFMediaObjectIndexObjectV1 *)operator new(0x58u);
      if ( !v20 )
        goto LABEL_105;
      v7 = CASFMediaObjectIndexObjectV1::CASFMediaObjectIndexObjectV1(v20);
      goto LABEL_103;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfSMPTEIndexParametersObject, 0x10u) )
    {
      v21 = (CASFSMPTEIndexParametersObjectV1 *)operator new(0x48u);
      if ( !v21 )
        goto LABEL_105;
      v7 = CASFSMPTEIndexParametersObjectV1::CASFSMPTEIndexParametersObjectV1(v21);
      goto LABEL_103;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfSMPTEIndexObject, 0x10u) )
    {
      v22 = (CASFSMPTEIndexObjectV1 *)operator new(0x60u);
      if ( !v22 )
        goto LABEL_105;
      v7 = CASFSMPTEIndexObjectV1::CASFSMPTEIndexObjectV1(v22);
      goto LABEL_103;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfErrorCorrectionObjectV0, 0x10u) )
    {
      v7 = (CASFMutualExclusionObjectEx *)operator new(0x58u);
      if ( !v7 )
        goto LABEL_105;
      *((_QWORD *)v7 + 5) = 0;
      *(_QWORD *)v7 = &CASFErrorCorrectionObject::`vftable';
      *((_QWORD *)v7 + 6) = 1;
      v23 = CLSID_CAsfErrorCorrectionObjectV0;
      *((_DWORD *)v7 + 2) = 109;
LABEL_78:
      *((GUID *)v7 + 1) = v23;
      *((_QWORD *)v7 + 10) = 0;
      *((_DWORD *)v7 + 18) = 0;
      goto LABEL_79;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfClockObjectV0, 0x10u) )
    {
      v7 = (CASFMutualExclusionObjectEx *)operator new(0x58u);
      if ( v7 )
      {
        *((_QWORD *)v7 + 5) = 0;
        *(_QWORD *)v7 = &CASFClockObject::`vftable';
        *((_QWORD *)v7 + 6) = 1;
        *((_DWORD *)v7 + 2) = 104;
        *((_QWORD *)v7 + 10) = 0;
        *((GUID *)v7 + 1) = CLSID_CAsfClockObjectV0;
        *((_DWORD *)v7 + 19) = 0;
        goto LABEL_79;
      }
      goto LABEL_105;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfScriptCommandObjectV0, 0x10u) )
    {
      v24 = (GUID *)operator new(0x60u);
      if ( v24 )
      {
        *(_QWORD *)v24[2].Data4 = 0;
        *(_QWORD *)&v24[3].Data1 = 1;
        *(_QWORD *)&v24->Data1 = &CASFScriptCommandObject::`vftable';
        *(_DWORD *)v24->Data4 = 116;
        *(_DWORD *)v24[4].Data4 = 0;
        v24[1] = CLSID_CAsfScriptCommandObjectV0;
        *(_QWORD *)&v24[5].Data1 = 0;
        *(_QWORD *)v24[5].Data4 = 0;
        *a2 = (struct CASFLonghandObject *)v24;
        *(_DWORD *)&v24->Data4[4] = 0;
        goto LABEL_153;
      }
      goto LABEL_105;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfCodecObjectV0, 0x10u) )
    {
      v7 = (CASFMutualExclusionObjectEx *)operator new(0x58u);
      if ( !v7 )
        goto LABEL_105;
      *((_QWORD *)v7 + 5) = 0;
      *(_QWORD *)v7 = &CASFCodecObject::`vftable';
      *((_QWORD *)v7 + 6) = 1;
      v23 = CLSID_CAsfCodecObjectV0;
      *((_DWORD *)v7 + 2) = 117;
      goto LABEL_78;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfMutualExclusionObject, 0x10u) )
    {
      v25 = (char *)operator new(0x58u);
      v16 = (struct CASFLonghandObject *)v25;
      if ( !v25 )
        goto LABEL_105;
      *((_QWORD *)v25 + 5) = 0;
      *((_QWORD *)v25 + 6) = 1;
      *(_QWORD *)v25 = &CASFMutualExclusionObject::`vftable';
      *((_DWORD *)v25 + 2) = 118;
      *((GUID *)v25 + 1) = CLSID_CAsfMutualExclusionObject;
      *(_OWORD *)(v25 + 56) = 0;
      *((_WORD *)v25 + 36) = 0;
      *((_QWORD *)v25 + 10) = 0;
LABEL_96:
      *a2 = v16;
      *((_DWORD *)v16 + 3) = 0;
      goto LABEL_153;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfMutualExclusionObjectEx, 0x10u) )
    {
      v26 = (CASFMutualExclusionObjectEx *)operator new(0x58u);
      if ( !v26 )
        goto LABEL_105;
      v7 = CASFMutualExclusionObjectEx::CASFMutualExclusionObjectEx(v26);
      goto LABEL_103;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfGroupMutualExclusionObject, 0x10u) )
    {
      v27 = (CASFGroupMutualExclusionObject *)operator new(0x188u);
      if ( !v27 )
        goto LABEL_105;
      v7 = CASFGroupMutualExclusionObject::CASFGroupMutualExclusionObject(v27);
      goto LABEL_103;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfStreamPrioritizationObject, 0x10u) )
    {
      v28 = (CASFStreamPrioritizationObject *)operator new(0xC0u);
      if ( !v28 )
        goto LABEL_105;
      v7 = CASFStreamPrioritizationObject::CASFStreamPrioritizationObject(v28);
      goto LABEL_103;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfBandwidthSharingObject, 0x10u) )
    {
      v29 = (char *)operator new(0x60u);
      v16 = (struct CASFLonghandObject *)v29;
      if ( !v29 )
        goto LABEL_105;
      *((_QWORD *)v29 + 5) = 0;
      *((_DWORD *)v29 + 2) = 100;
      *((_QWORD *)v29 + 6) = 1;
      *(_QWORD *)v29 = &CASFBandwidthSharingObject::`vftable';
      *((_QWORD *)v29 + 9) = 0;
      *((_WORD *)v29 + 40) = 0;
      *(GUID *)(v29 + 56) = CLSID_BandwidthSharingPartial;
      *((_QWORD *)v29 + 11) = 0;
      v17 = CLSID_CAsfBandwidthSharingObject;
LABEL_95:
      *((GUID *)v16 + 1) = v17;
      goto LABEL_96;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CASFV1LanguageListObject, 0x10u) )
    {
      v30 = (CASFV1LanguageListObject *)operator new(0x118u);
      if ( !v30 )
        goto LABEL_105;
      v7 = CASFV1LanguageListObject::CASFV1LanguageListObject(v30);
      goto LABEL_103;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfExtendedStreamPropertiesObject, 0x10u) )
    {
      v31 = (CASFExtendedStreamPropertiesObject *)operator new(0x118u);
      if ( !v31 )
        goto LABEL_105;
      v7 = CASFExtendedStreamPropertiesObject::CASFExtendedStreamPropertiesObject(v31);
      goto LABEL_103;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfContentBrandingObject, 0x10u) )
    {
      v32 = (CASFAdvancedContentEncryptionObject *)operator new(0x60u);
      if ( v32 )
      {
        *((_QWORD *)v32 + 5) = 0;
        *(_QWORD *)v32 = &CASFContentBrandingObject::`vftable';
        *((_QWORD *)v32 + 6) = 1;
        v33 = CLSID_CAsfContentBrandingObject;
        *((_QWORD *)v32 + 1) = 120;
        *((_QWORD *)v32 + 8) = 0;
        *((_DWORD *)v32 + 18) = 0;
        *((_DWORD *)v32 + 14) = 0;
LABEL_109:
        *((GUID *)v32 + 1) = v33;
        *((_QWORD *)v32 + 10) = 0;
        *((_QWORD *)v32 + 11) = 0;
LABEL_152:
        *a2 = v32;
LABEL_153:
        if ( !*a2 )
          return -2147024882;
        v40 = (*(__int64 (__fastcall **)(_QWORD, struct CASFArchive *))(*(_QWORD *)*a2 + 16LL))(*a2, a3);
        if ( v40 >= 0 )
          return 0;
        if ( *a2 )
          (**(void (__fastcall ***)(_QWORD, __int64))*a2)(*a2, 1);
        return v40;
      }
      goto LABEL_151;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfContentEncryptionObject, 0x10u) )
    {
      v32 = (CASFAdvancedContentEncryptionObject *)operator new(0x60u);
      if ( v32 )
      {
        *((_QWORD *)v32 + 5) = 0;
        *(_QWORD *)v32 = &CASFContentEncryptionObject::`vftable';
        *((_QWORD *)v32 + 6) = 1;
        v33 = CLSID_CAsfContentEncryptionObject;
        *((_QWORD *)v32 + 1) = 121;
        *((_QWORD *)v32 + 7) = 0;
        *((_DWORD *)v32 + 16) = 0;
        *((_QWORD *)v32 + 9) = 0;
        goto LABEL_109;
      }
LABEL_151:
      v32 = 0;
      goto LABEL_152;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfAdvancedContentEncryptionObject, 0x10u) )
    {
      v34 = (CASFAdvancedContentEncryptionObject *)operator new(0x118u);
      if ( v34 )
      {
        v32 = CASFAdvancedContentEncryptionObject::CASFAdvancedContentEncryptionObject(v34);
        goto LABEL_152;
      }
      goto LABEL_151;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfDigitalSignatureObject, 0x10u) )
    {
      v32 = (CASFAdvancedContentEncryptionObject *)operator new(0x48u);
      if ( !v32 )
        goto LABEL_151;
      *((_QWORD *)v32 + 5) = 0;
      *(_QWORD *)v32 = &CASFDigitalSignatureObject::`vftable';
      *((_QWORD *)v32 + 6) = 1;
      v35 = CLSID_CAsfDigitalSignatureObject;
      *((_QWORD *)v32 + 1) = 122;
LABEL_119:
      *((GUID *)v32 + 1) = v35;
      *((_QWORD *)v32 + 7) = 0;
      goto LABEL_120;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfExtendedContentDescObject, 0x10u) )
    {
      v32 = (CASFAdvancedContentEncryptionObject *)operator new(0x48u);
      if ( !v32 )
        goto LABEL_151;
      *((_QWORD *)v32 + 5) = 0;
      *(_QWORD *)v32 = &CASFExtendedContentDescObject::`vftable';
      *((_QWORD *)v32 + 6) = 1;
      *((_QWORD *)v32 + 1) = 123;
      *((_WORD *)v32 + 28) = 0;
      *((GUID *)v32 + 1) = CLSID_CAsfExtendedContentDescObject;
LABEL_120:
      *((_QWORD *)v32 + 8) = 0;
      goto LABEL_152;
    }
    if ( !memcmp_0(&Buf1, &CLSID_CAsfContentEncryptionObjectEx, 0x10u) )
    {
      v32 = (CASFAdvancedContentEncryptionObject *)operator new(0x48u);
      if ( !v32 )
        goto LABEL_151;
      *((_QWORD *)v32 + 5) = 0;
      *(_QWORD *)v32 = &CASFContentEncryptionObjectEx::`vftable';
      *((_QWORD *)v32 + 6) = 1;
      v36 = CLSID_CAsfContentEncryptionObjectEx;
      *((_QWORD *)v32 + 1) = 124;
    }
    else
    {
      if ( memcmp_0(&Buf1, &CLSID_CAsfContentEncryptionObjectEx2, 0x10u) )
      {
        if ( memcmp_0(&Buf1, &CLSID_CAsfLicenseStoreObject, 0x10u) )
        {
          if ( !memcmp_0(&Buf1, &CLSID_CAsfPaddingObject, 0x10u) )
          {
            v32 = (CASFAdvancedContentEncryptionObject *)operator new(0x38u);
            if ( v32 )
            {
              *((_QWORD *)v32 + 5) = 0;
              *(_QWORD *)v32 = &CASFIndexParametersPlaceholderObject::`vftable';
              *((_DWORD *)v32 + 3) = 0;
              *((_QWORD *)v32 + 6) = 1;
              *((_DWORD *)v32 + 2) = 126;
              *((_QWORD *)v32 + 4) = 4096;
              *((GUID *)v32 + 1) = CLSID_CAsfPaddingObject;
              goto LABEL_152;
            }
          }
          else if ( !memcmp_0(&Buf1, &CLSID_CAsfIndexParametersPlaceholderObject, 0x10u) )
          {
            v37 = (CASFIndexParametersPlaceholderObject *)operator new(0x38u);
            if ( v37 )
            {
              v32 = CASFIndexParametersPlaceholderObject::CASFIndexParametersPlaceholderObject(v37);
              goto LABEL_152;
            }
          }
          else if ( !memcmp_0(&Buf1, &CLSID_CAsfCompatibilityObject, 0x10u) )
          {
            v32 = (CASFAdvancedContentEncryptionObject *)operator new(0x40u);
            if ( v32 )
            {
              *((_QWORD *)v32 + 5) = 0;
              *(_QWORD *)v32 = &CASFCompatibilityObject::`vftable';
              *((_QWORD *)v32 + 1) = 100;
              *((_QWORD *)v32 + 6) = 1;
              *((_WORD *)v32 + 28) = 258;
              *((GUID *)v32 + 1) = CLSID_CAsfCompatibilityObject;
              goto LABEL_152;
            }
          }
          else if ( !memcmp_0(&Buf1, &CLSID_CAsfV1MetadataObject, 0x10u) )
          {
            v38 = (CASFV1MetadataObject *)operator new(0x290u);
            if ( v38 )
            {
              v32 = CASFV1MetadataObject::CASFV1MetadataObject(v38);
              goto LABEL_152;
            }
          }
          else if ( !memcmp_0(&Buf1, &CLSID_CAsfV1MetadataLibraryObject, 0x10u) )
          {
            v39 = (CASFV1MetadataLibraryObject *)operator new(0x290u);
            if ( v39 )
            {
              v32 = CASFV1MetadataLibraryObject::CASFV1MetadataLibraryObject(v39);
              goto LABEL_152;
            }
          }
          else
          {
            v32 = (CASFAdvancedContentEncryptionObject *)operator new(0x40u);
            if ( v32 )
            {
              *((_QWORD *)v32 + 5) = 0;
              *(_QWORD *)v32 = &CASFUnknownObject::`vftable';
              *((_QWORD *)v32 + 6) = 1;
              *((_QWORD *)v32 + 4) = 0;
              *((_QWORD *)v32 + 7) = 0;
              *((_QWORD *)v32 + 1) = 115;
              goto LABEL_152;
            }
          }
          goto LABEL_151;
        }
        v32 = (CASFAdvancedContentEncryptionObject *)operator new(0x48u);
        if ( !v32 )
          goto LABEL_151;
        *((_QWORD *)v32 + 5) = 0;
        *(_QWORD *)v32 = &CASFLicenseStoreObject::`vftable';
        *((_QWORD *)v32 + 6) = 1;
        v35 = CLSID_CAsfLicenseStoreObject;
        *((_QWORD *)v32 + 1) = 125;
        goto LABEL_119;
      }
      v32 = (CASFAdvancedContentEncryptionObject *)operator new(0x48u);
      if ( !v32 )
        goto LABEL_151;
      *((_QWORD *)v32 + 5) = 0;
      *(_QWORD *)v32 = &CASFContentEncryptionObjectEx2::`vftable';
      *((_QWORD *)v32 + 6) = 1;
      v36 = CLSID_CAsfContentEncryptionObjectEx2;
      *((_QWORD *)v32 + 1) = 130;
      *((_DWORD *)v32 + 17) = 9;
    }
    *((GUID *)v32 + 1) = v36;
    *((_QWORD *)v32 + 7) = 0;
    *((_DWORD *)v32 + 16) = 0;
    goto LABEL_152;
  }
  return result;
}

```

## disassembly

```asm
0x180012080  mov     [rsp-28h+arg_0], rbx
0x180012085  push    rbp
0x180012086  push    rsi
0x180012087  push    rdi
0x180012088  push    r14
0x18001208a  push    r15
0x18001208c  mov     rbp, rsp
0x18001208f  sub     rsp, 70h
0x180012093  mov     rax, cs:__security_cookie
0x18001209a  xor     rax, rsp
0x18001209d  mov     [rbp+var_8], rax
0x1800120a1  xor     r14d, r14d
0x1800120a4  mov     rsi, r8
0x1800120a7  mov     rbx, rdx
0x1800120aa  test    rdx, rdx
0x1800120ad  jnz     short loc_1800120B9
0x1800120af  mov     eax, 80070057h
0x1800120b4  jmp     loc_180012E10
0x1800120b9  mov     [rdx], r14
0x1800120bc  lea     rax, ??_7CASFLonghandObject@@6B@; const CASFLonghandObject::`vftable'
0x1800120c3  mov     rdi, [r8+8]
0x1800120c7  lea     rcx, [rbp+var_40]; this
0x1800120cb  mov     r15d, 1
0x1800120d1  mov     [rbp+var_40], rax
0x1800120d5  mov     rdx, rsi; struct CASFArchive *
0x1800120d8  mov     [rbp+var_10], r15
0x1800120dc  mov     [rbp+var_18], r14
0x1800120e0  mov     [rbp+var_38], 64h ; 'd'
0x1800120e8  call    ?Restore@CASFLonghandObject@@UEAAJAEAVCASFArchive@@@Z; CASFLonghandObject::Restore(CASFArchive &)
0x1800120ed  test    eax, eax
0x1800120ef  js      loc_180012E10
0x1800120f5  cmp     rdi, [rsi]
0x1800120f8  jb      short loc_180012104
0x1800120fa  cmp     rdi, [rsi+10h]
0x1800120fe  ja      short loc_180012104
0x180012100  mov     [rsi+8], rdi
0x180012104  mov     ecx, [rsi+10h]
0x180012107  sub     ecx, [rsi]
0x180012109  sub     rcx, [rsi+8]
0x18001210d  add     rcx, [rsi]
0x180012110  cmp     [rbp+var_20], rcx
0x180012114  jbe     short loc_180012120
0x180012116  mov     eax, 0C00D07D0h
0x18001211b  jmp     loc_180012E10
0x180012120  movups  xmm0, [rbp+var_30]
0x180012124  mov     edi, 10h
0x180012129  lea     rdx, CLSID_CAsfHeaderObjectV0; Buf2
0x180012130  mov     r8d, edi; Size
0x180012133  lea     rcx, [rbp+Buf1]; Buf1
0x180012137  movdqu  [rbp+Buf1], xmm0
0x18001213c  call    memcmp_0
0x180012141  test    eax, eax
0x180012143  jnz     short loc_180012180
0x180012145  lea     ecx, [rdi+30h]; Size
0x180012148  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001214d  test    rax, rax
0x180012150  jz      loc_1800129A3
0x180012156  lea     rcx, ??_7CASFHeaderObject@@6B@; const CASFHeaderObject::`vftable'
0x18001215d  mov     [rax+28h], r14
0x180012161  mov     [rax], rcx
0x180012164  mov     [rax+30h], r15
0x180012168  movups  xmm0, xmmword ptr cs:CLSID_CAsfHeaderObjectV0.Data1
0x18001216f  mov     dword ptr [rax+8], 65h ; 'e'
0x180012176  movdqu  xmmword ptr [rax+10h], xmm0
0x18001217b  jmp     loc_1800127AB
0x180012180  mov     r8, rdi; Size
0x180012183  lea     rdx, CLSID_CAsfPropertiesObjectV0; Buf2
0x18001218a  lea     rcx, [rbp+Buf1]; Buf1
0x18001218e  call    memcmp_0
0x180012193  test    eax, eax
0x180012195  jnz     short loc_1800121D4
0x180012197  mov     ecx, 98h; Size
0x18001219c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800121a1  test    rax, rax
0x1800121a4  jz      loc_1800129A3
0x1800121aa  lea     rcx, ??_7CDVRASFPropertiesObject@@6B@; const CDVRASFPropertiesObject::`vftable'
0x1800121b1  mov     [rax+28h], r14
0x1800121b5  mov     [rax], rcx
0x1800121b8  mov     [rax+30h], r15
0x1800121bc  movups  xmm0, xmmword ptr cs:CLSID_CAsfPropertiesObjectV2.Data1
0x1800121c3  mov     dword ptr [rax+8], 66h ; 'f'
0x1800121ca  movdqu  xmmword ptr [rax+10h], xmm0
0x1800121cf  jmp     loc_1800127AB
0x1800121d4  mov     r8, rdi; Size
0x1800121d7  lea     rdx, CLSID_CAsfPropertiesObjectV1; Buf2
0x1800121de  lea     rcx, [rbp+Buf1]; Buf1
0x1800121e2  call    memcmp_0
0x1800121e7  test    eax, eax
0x1800121e9  jnz     short loc_18001222B
0x1800121eb  mov     ecx, 98h; Size
0x1800121f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800121f5  test    rax, rax
0x1800121f8  jz      loc_1800129A3
0x1800121fe  mov     [rax+28h], r14
0x180012202  lea     rcx, ??_7CDVRASFPropertiesObject@@6B@; const CDVRASFPropertiesObject::`vftable'
0x180012209  mov     [rax], rcx
0x18001220c  mov     [rax+30h], r15
0x180012210  movups  xmm0, xmmword ptr cs:CLSID_CAsfPropertiesObjectV2.Data1
0x180012217  mov     dword ptr [rax+8], 66h ; 'f'
0x18001221e  movdqu  xmmword ptr [rax+10h], xmm0
0x180012223  mov     [rbx], rax
0x180012226  jmp     loc_1800122F7
0x18001222b  mov     r8, rdi; Size
0x18001222e  lea     rdx, CLSID_CAsfPropertiesObjectV2; Buf2
0x180012235  lea     rcx, [rbp+Buf1]; Buf1
0x180012239  call    memcmp_0
0x18001223e  test    eax, eax
0x180012240  jnz     short loc_180012282
0x180012242  mov     ecx, 98h; Size
0x180012247  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001224c  test    rax, rax
0x18001224f  jz      loc_1800129A3
0x180012255  mov     [rax+28h], r14
0x180012259  lea     rcx, ??_7CDVRASFPropertiesObject@@6B@; const CDVRASFPropertiesObject::`vftable'
0x180012260  mov     [rax], rcx
0x180012263  mov     [rax+30h], r15
0x180012267  movups  xmm0, xmmword ptr cs:CLSID_CAsfPropertiesObjectV2.Data1
0x18001226e  mov     dword ptr [rax+8], 66h ; 'f'
0x180012275  movdqu  xmmword ptr [rax+10h], xmm0
0x18001227a  mov     [rbx], rax
0x18001227d  jmp     loc_18001233E
0x180012282  mov     r8, rdi; Size
0x180012285  lea     rdx, CLSID_CAsfStreamPropertiesObjectV0; Buf2
0x18001228c  lea     rcx, [rbp+Buf1]; Buf1
0x180012290  call    memcmp_0
0x180012295  test    eax, eax
0x180012297  jnz     short loc_1800122B9
0x180012299  mov     ecx, 88h; Size
0x18001229e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800122a3  test    rax, rax
0x1800122a6  jz      loc_1800129A3
0x1800122ac  mov     rcx, rax; this
0x1800122af  call    ??0CASFStreamPropertiesObject@@QEAA@XZ; CASFStreamPropertiesObject::CASFStreamPropertiesObject(void)
0x1800122b4  jmp     loc_18001298E
0x1800122b9  mov     r8, rdi; Size
0x1800122bc  lea     rdx, CLSID_CAsfStreamPropertiesObjectV1; Buf2
0x1800122c3  lea     rcx, [rbp+Buf1]; Buf1
0x1800122c7  call    memcmp_0
0x1800122cc  test    eax, eax
0x1800122ce  jnz     short loc_180012300
0x1800122d0  mov     ecx, 88h; Size
0x1800122d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800122da  test    rax, rax
0x1800122dd  jz      loc_1800129A3
0x1800122e3  mov     rcx, rax; this
0x1800122e6  call    ??0CASFStreamPropertiesObject@@QEAA@XZ; CASFStreamPropertiesObject::CASFStreamPropertiesObject(void)
0x1800122eb  mov     [rbx], rax
0x1800122ee  test    rax, rax
0x1800122f1  jz      loc_180012DD0
0x1800122f7  mov     [rax+0Ch], r15d
0x1800122fb  jmp     loc_180012DD0
0x180012300  mov     r8, rdi; Size
0x180012303  lea     rdx, CLSID_CAsfStreamPropertiesObjectV2; Buf2
0x18001230a  lea     rcx, [rbp+Buf1]; Buf1
0x18001230e  call    memcmp_0
0x180012313  test    eax, eax
0x180012315  jnz     short loc_18001234A
0x180012317  mov     ecx, 88h; Size
0x18001231c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012321  test    rax, rax
0x180012324  jz      loc_1800129A3
0x18001232a  mov     rcx, rax; this
0x18001232d  call    ??0CASFStreamPropertiesObject@@QEAA@XZ; CASFStreamPropertiesObject::CASFStreamPropertiesObject(void)
0x180012332  mov     [rbx], rax
0x180012335  test    rax, rax
0x180012338  jz      loc_180012DD0
0x18001233e  mov     dword ptr [rax+0Ch], 2
0x180012345  jmp     loc_180012DD0
0x18001234a  mov     r8, rdi; Size
0x18001234d  lea     rdx, CLSID_CAsfStreamPropertiesObjectEx; Buf2
0x180012354  lea     rcx, [rbp+Buf1]; Buf1
0x180012358  call    memcmp_0
0x18001235d  test    eax, eax
0x18001235f  jnz     short loc_180012381
0x180012361  mov     ecx, 248h; Size
0x180012366  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001236b  test    rax, rax
0x18001236e  jz      loc_1800129A3
0x180012374  mov     rcx, rax; this
0x180012377  call    ??0CASFStreamPropertiesObjectEx@@QEAA@XZ; CASFStreamPropertiesObjectEx::CASFStreamPropertiesObjectEx(void)
0x18001237c  jmp     loc_18001298E
0x180012381  mov     r8, rdi; Size
0x180012384  lea     rdx, CLSID_CAsfContentDescriptionObjectV0; Buf2
0x18001238b  lea     rcx, [rbp+Buf1]; Buf1
0x18001238f  call    memcmp_0
0x180012394  test    eax, eax
0x180012396  jnz     short loc_1800123B6
0x180012398  lea     ecx, [rax+70h]; Size
0x18001239b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800123a0  test    rax, rax
0x1800123a3  jz      loc_1800129A3
0x1800123a9  mov     rcx, rax; this
0x1800123ac  call    ??0CASFContentDescriptionObject@@QEAA@XZ; CASFContentDescriptionObject::CASFContentDescriptionObject(void)
0x1800123b1  jmp     loc_18001298E
0x1800123b6  mov     r8, rdi; Size
0x1800123b9  lea     rdx, CLSID_CAsfDataObjectV0; Buf2
0x1800123c0  lea     rcx, [rbp+Buf1]; Buf1
0x1800123c4  call    memcmp_0
0x1800123c9  test    eax, eax
0x1800123cb  jnz     short loc_180012408
0x1800123cd  lea     ecx, [rax+58h]; Size
0x1800123d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800123d5  test    rax, rax
0x1800123d8  jz      loc_1800129A3
0x1800123de  lea     rcx, ??_7CDVRASFDataObject@@6B@; const CDVRASFDataObject::`vftable'
0x1800123e5  mov     [rax+28h], r14
0x1800123e9  mov     [rax], rcx
0x1800123ec  mov     [rax+30h], r15
0x1800123f0  movups  xmm0, xmmword ptr cs:CLSID_CAsfDataObjectV0.Data1
0x1800123f7  mov     dword ptr [rax+8], 72h ; 'r'
0x1800123fe  movdqu  xmmword ptr [rax+10h], xmm0
0x180012403  jmp     loc_1800127AB
0x180012408  mov     r8, rdi; Size
0x18001240b  lea     rdx, CLSID_CAsfIndexObjectV0; Buf2
0x180012412  lea     rcx, [rbp+Buf1]; Buf1
0x180012416  call    memcmp_0
0x18001241b  test    eax, eax
0x18001241d  jnz     short loc_18001246B
0x18001241f  mov     ecx, 60h ; '`'; Size
0x180012424  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012429  mov     rcx, rax
0x18001242c  test    rax, rax
0x18001242f  jz      loc_1800129A3
0x180012435  mov     [rax+28h], r14
0x180012439  mov     [rax+30h], r15
0x18001243d  lea     rax, ??_7CASFMarkerObject@@6B@; const CASFMarkerObject::`vftable'
0x180012444  mov     [rcx], rax
0x180012447  movups  xmm0, xmmword ptr cs:CLSID_CAsfMarkerObjectV0.Data1
0x18001244e  mov     dword ptr [rcx+8], 6Bh ; 'k'
0x180012455  mov     [rcx+50h], r14
0x180012459  mov     [rcx+4Eh], r14w
0x18001245e  mov     [rcx+58h], r14
0x180012462  mov     [rcx+48h], r14d
0x180012466  jmp     loc_18001291F
0x18001246b  mov     r8, rdi; Size
0x18001246e  lea     rdx, CLSID_CAsfMarkerObjectV0; Buf2
0x180012475  lea     rcx, [rbp+Buf1]; Buf1
0x180012479  call    memcmp_0
0x18001247e  test    eax, eax
0x180012480  jz      short loc_18001241F
0x180012482  mov     r8, rdi; Size
0x180012485  lea     rdx, CLSID_CAsfIndexObjectV2; Buf2
0x18001248c  lea     rcx, [rbp+Buf1]; Buf1
0x180012490  call    memcmp_0
0x180012495  test    eax, eax
0x180012497  jnz     short loc_1800124DC
0x180012499  lea     ecx, [rax+60h]; Size
0x18001249c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800124a1  test    rax, rax
0x1800124a4  jz      loc_1800129A3
0x1800124aa  lea     rcx, ??_7CASFIndexObject@@6B@; const CASFIndexObject::`vftable'
0x1800124b1  mov     [rax+28h], r14
0x1800124b5  mov     [rax], rcx
0x1800124b8  mov     [rax+30h], r15
0x1800124bc  movups  xmm0, xmmword ptr cs:CLSID_CAsfIndexObjectV2.Data1
0x1800124c3  mov     dword ptr [rax+8], 6Ch ; 'l'
0x1800124ca  mov     [rax+58h], r14
0x1800124ce  movdqu  xmmword ptr [rax+10h], xmm0
0x1800124d3  mov     [rax+50h], r14
0x1800124d7  jmp     loc_1800127AB
0x1800124dc  mov     r8, rdi; Size
0x1800124df  lea     rdx, CLSID_CAsfIndexParametersObject; Buf2
0x1800124e6  lea     rcx, [rbp+Buf1]; Buf1
0x1800124ea  call    memcmp_0
0x1800124ef  test    eax, eax
0x1800124f1  jnz     short loc_18001253E
0x1800124f3  lea     ecx, [rax+48h]; Size
0x1800124f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800124fb  test    rax, rax
0x1800124fe  jz      loc_1800129A3
0x180012504  lea     rcx, ??_7CASFIndexParametersObject@@6B@; const CASFIndexParametersObject::`vftable'
0x18001250b  mov     [rax+28h], r14
0x18001250f  mov     [rax], rcx
0x180012512  mov     dword ptr [rax+8], 64h ; 'd'
0x180012519  mov     [rax+30h], r15
0x18001251d  movups  xmm0, xmmword ptr cs:CLSID_CAsfIndexParametersObject.Data1
0x180012524  mov     dword ptr [rax+38h], 3E8h
0x18001252b  mov     [rax+3Ch], r14w
0x180012530  movdqu  xmmword ptr [rax+10h], xmm0
0x180012535  mov     [rax+40h], r14
0x180012539  jmp     loc_1800127AB
0x18001253e  mov     r8, rdi; Size
0x180012541  lea     rdx, CLSID_CAsfIndexObjectEx; Buf2
0x180012548  lea     rcx, [rbp+Buf1]; Buf1
0x18001254c  call    memcmp_0
0x180012551  test    eax, eax
0x180012553  jnz     short loc_180012573
0x180012555  lea     ecx, [rax+58h]; Size
0x180012558  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001255d  test    rax, rax
0x180012560  jz      loc_1800129A3
0x180012566  mov     rcx, rax; this
0x180012569  call    ??0CASFIndexObjectEx@@QEAA@XZ; CASFIndexObjectEx::CASFIndexObjectEx(void)
0x18001256e  jmp     loc_18001298E
0x180012573  mov     r8, rdi; Size
0x180012576  lea     rdx, CLSID_CAsfMediaObjectIndexParametersObject; Buf2
0x18001257d  lea     rcx, [rbp+Buf1]; Buf1
0x180012581  call    memcmp_0
0x180012586  test    eax, eax
0x180012588  jnz     short loc_1800125A8
  ... truncated ...
```
