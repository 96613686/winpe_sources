# SampRetrieveUserPasswords

- ea: `0x180016d50`
- end: `0x180017a58`
- name: `SampRetrieveUserPasswords`
- size: `3336`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, struct _LM_OWF_PASSWORD *, _BYTE *, struct _LM_OWF_PASSWORD *, _BYTE *, bool *)`
- caller_count: `7`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000b150`
- `0x18008db68`
- `0x18009df30`
- `0x18009e244`
- `0x1800a0a58`
- `0x1800a2934`
- `0x1800a5e40`

## callees

- `0x180016d50`
- `0x180018620`
- `0x180018f10`
- `0x18001a8e0`
- `0x180027250`
- `0x180027e24`
- `0x1800281e4`
- `0x18002820c`
- `0x180028270`
- `0x1800282b8`
- `0x18002832c`
- `0x18002cd80`
- `0x180037284`
- `0x18003c010`
- `0x18003c920`
- `0x18006ae40`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x18001729e`
- `ntdll!RtlCopyUnicodeString` at `0x180017899`
- `ntdll!RtlCopyUnicodeString` at `0x18001729e`
- `ntdll!RtlCopyUnicodeString` at `0x180017899`
- `ntdll!RtlInitUnicodeString` at `0x1800172ac`
- `ntdll!RtlInitUnicodeString` at `0x1800178a7`
- `ntdll!RtlInitUnicodeString` at `0x1800172ac`
- `ntdll!RtlInitUnicodeString` at `0x1800178a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800170b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001723e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800176ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017839`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800170b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001723e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800176ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017839`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016de3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800173d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001743f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800179f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016de3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800173d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001743f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800179f6`
- `bcrypt!BCryptDestroyKey` at `0x1800171ba`
- `bcrypt!BCryptDestroyKey` at `0x1800177d2`
- `bcrypt!BCryptDestroyKey` at `0x1800171ba`
- `bcrypt!BCryptDestroyKey` at `0x1800177d2`
- `CRYPTSP!SystemFunction027` at `0x18001796e`
- `CRYPTSP!SystemFunction027` at `0x18001796e`
- `CRYPTSP!SystemFunction025` at `0x18001736f`
- `CRYPTSP!SystemFunction025` at `0x18001736f`
- `CRYPTSP!SystemFunction031` at `0x180017984`
- `CRYPTSP!SystemFunction031` at `0x180017984`

## pseudocode

```c
__int64 __fastcall SampRetrieveUserPasswords(
        struct _SAMP_OBJECT *a1,
        struct _LM_OWF_PASSWORD *a2,
        _BYTE *a3,
        struct _LM_OWF_PASSWORD *a4,
        _BYTE *a5,
        bool *a6)
{
  bool v6; // zf
  struct _LM_OWF_PASSWORD *v7; // rdi
  void *v11; // rcx
  __int64 v12; // rax
  int v13; // ebx
  int v14; // eax
  PUNICODE_STRING v15; // r10
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rax
  int v19; // ecx
  unsigned __int8 IsDataEncrypted; // al
  unsigned int v21; // r8d
  PWSTR Buffer; // rdi
  int v23; // eax
  PUNICODE_STRING v24; // rcx
  int v25; // eax
  __int64 v26; // rdx
  UCHAR *v27; // rbx
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rdx
  __int64 Length; // rcx
  PWSTR v32; // rax
  void *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  PUNICODE_STRING v36; // r10
  PWSTR v37; // rcx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // rax
  int v41; // ecx
  unsigned __int8 v42; // al
  unsigned int v43; // r8d
  PWSTR v44; // rbx
  int v45; // eax
  int v46; // eax
  __int64 v47; // rdx
  __int64 *v48; // r8
  __int64 v49; // rdx
  __int64 *v50; // r8
  UCHAR *v51; // rsi
  __int64 v52; // rax
  int v53; // eax
  char v54; // al
  bool *v55; // rax
  __int64 v56; // rcx
  PWSTR v57; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-79h] BYREF
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v61; // [rsp+50h] [rbp-59h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v63; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v64; // [rsp+68h] [rbp-41h] BYREF
  unsigned int v65; // [rsp+6Ch] [rbp-3Dh] BYREF
  struct _LM_OWF_PASSWORD *v66; // [rsp+70h] [rbp-39h]
  _BYTE *v67; // [rsp+78h] [rbp-31h]
  bool *v68; // [rsp+80h] [rbp-29h]
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+88h] [rbp-21h] BYREF
  __int64 v70; // [rsp+98h] [rbp-11h]

  v6 = (*((_BYTE *)a1 + 192) & 2) == 0;
  v67 = a5;
  v7 = a4;
  v68 = a6;
  v61 = *((_DWORD *)a1 + 62);
  v65 = v61;
  v66 = a4;
  DestinationString = 0;
  SourceString = 0;
  if ( v6 )
  {
    v14 = SampValidateRegAttributes(a1, 1u);
    goto LABEL_13;
  }
  if ( *((_QWORD *)a1 + 14) )
  {
    if ( _bittest64(*((const signed __int64 **)a1 + 8), 0xDu) )
    {
      v11 = (void *)*((_QWORD *)a1 + 17);
      if ( v11 )
        LocalFree(v11);
      v12 = *((_QWORD *)a1 + 14);
      *((_BYTE *)a1 + 20) &= 0xF0u;
      *((_QWORD *)a1 + 17) = v12;
      *((_QWORD *)a1 + 14) = 0;
      *((_QWORD *)a1 + 15) = 0;
      *((_DWORD *)a1 + 32) = 0;
      v13 = SampValidateDsAttributes(a1, 0);
      if ( v13 >= 0 )
      {
        v13 = SampValidateDsAttributes(a1, 1u);
        if ( v13 >= 0 )
        {
          SampMarkPerAttributeInvalidFromWhichFields(a1, 0);
          *((_BYTE *)a1 + 29) &= ~1u;
        }
      }
      goto LABEL_14;
    }
    v14 = SampValidateDsAttributes(a1, 1u);
    goto LABEL_13;
  }
  v13 = SampValidateDsAttributes(a1, 0);
  if ( v13 >= 0 )
  {
    v14 = SampValidateDsAttributes(a1, 1u);
LABEL_13:
    v13 = v14;
  }
LABEL_14:
  v15 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      110,
      WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
      (unsigned int)v13,
      v13);
    v15 = WPP_GLOBAL_Control;
  }
  if ( v13 < 0 )
  {
    if ( (*(_DWORD *)(&v15[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      WPP_SF_Dd(v15[3].Buffer, 29, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids, (unsigned int)v13, v13);
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          188,
          WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
          (unsigned int)v13,
          v13);
    }
    return (unsigned int)v13;
  }
  v16 = *((_QWORD *)a1 + 14);
  v17 = 88LL * *((int *)a1 + 4);
  if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
  {
    v18 = *(unsigned int *)((char *)&SampObjectInformation + v17 + 76);
    SourceString.MaximumLength = *(_WORD *)(v18 + v16 + 160);
    SourceString.Length = SourceString.MaximumLength;
    v19 = *(_DWORD *)((char *)&SampObjectInformation + v17 + 72);
  }
  else
  {
    v18 = *(unsigned int *)((char *)&SampObjectInformation + v17 + 52);
    SourceString.MaximumLength = *(_WORD *)(v18 + v16 + 160);
    SourceString.Length = SourceString.MaximumLength;
    v19 = *(_DWORD *)((char *)&SampObjectInformation + v17 + 56);
  }
  SourceString.Buffer = (PWSTR)(v16 + (unsigned int)(*(_DWORD *)(v18 + v16 + 156) + v19));
  if ( (*(_DWORD *)(&v15[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v15[3].Buffer, 30, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids, 0, 0);
  IsDataEncrypted = SampIsDataEncrypted(a1, &SourceString);
  if ( SampSecretEncryptionEnabled )
  {
    if ( IsDataEncrypted )
    {
      Buffer = SourceString.Buffer;
      v23 = *SourceString.Buffer;
      if ( v23 != SampCurrentPEKID && v23 != SampPreviousPEKID )
      {
        v13 = -1073741595;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
          return (unsigned int)v13;
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          18,
          WPP_9bc989344d36314fcec0e76bff3b0413_Traceguids,
          3221225701LL,
          -1073741595);
        v24 = WPP_GLOBAL_Control;
        goto LABEL_64;
      }
      if ( (SourceString.Buffer[1] & 2) != 0 )
      {
        v25 = SampDecryptSecretDataWithAes(&DestinationString, &SourceString, v21);
        v24 = WPP_GLOBAL_Control;
        v13 = v25;
        v7 = v66;
        goto LABEL_61;
      }
      v63 = v61;
      v70 = 0;
      hKey = 0;
      DestinationString = 0;
      DestinationString.Length = SourceString.Length - 4;
      DestinationString.MaximumLength = SourceString.Length - 4;
      *(_OWORD *)phHash = 0;
      if ( SourceString.Length == 4 )
      {
        DestinationString.Buffer = 0;
        v24 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          v26 = 12;
LABEL_46:
          WPP_SF_Dd(v24[3].Buffer, v26, WPP_9bc989344d36314fcec0e76bff3b0413_Traceguids, 0, 0);
          v24 = WPP_GLOBAL_Control;
        }
      }
      else
      {
        DestinationString.Buffer = (PWSTR)LocalAlloc(0x40u, (unsigned __int16)(SourceString.Length - 4));
        if ( !DestinationString.Buffer )
        {
          v24 = WPP_GLOBAL_Control;
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control[3].Buffer,
              13,
              WPP_9bc989344d36314fcec0e76bff3b0413_Traceguids,
              3221225626LL,
              -1073741670);
            v24 = WPP_GLOBAL_Control;
          }
          v13 = -1073741670;
          goto LABEL_48;
        }
        v27 = &SampCurrentPEK;
        if ( *Buffer != SampCurrentPEKID )
          v27 = &SampPreviousPEK;
        CngRsa32Compat_MD5Init(phHash);
        CngRsa32Compat_MD5Update(phHash, v27, 16);
        CngRsa32Compat_MD5Update(phHash, &v63, 4);
        if ( (Buffer[1] & 1) != 0 )
        {
          v64 = 0;
          v28 = SampMagicConstantFromDataType(1, &v64);
          CngRsa32Compat_MD5Update(phHash, v28, v64);
        }
        CngRsa32Compat_MD5Final(phHash);
        CngRsa32Compat_rc4_key(&hKey);
        memcpy_0(DestinationString.Buffer, Buffer + 2, DestinationString.Length);
        CngRsa32Compat_rc4(&hKey, DestinationString.Length, DestinationString.Buffer);
        BCryptDestroyKey(hKey);
        hKey = 0;
        v24 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          v26 = 14;
          goto LABEL_46;
        }
      }
      v13 = 0;
LABEL_48:
      v7 = v66;
      goto LABEL_61;
    }
    if ( (SourceString.Length & 0xF) != 0 )
    {
      v29 = SampDuplicateUnicodeString(&DestinationString, &SampNullString);
      v24 = WPP_GLOBAL_Control;
      v13 = v29;
      goto LABEL_61;
    }
  }
  if ( SourceString.Length )
  {
    DestinationString.Buffer = (PWSTR)LocalAlloc(0x40u, SourceString.Length);
    if ( !DestinationString.Buffer )
    {
      v24 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          129,
          WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
          3221225626LL,
          -1073741670);
        v24 = WPP_GLOBAL_Control;
      }
      v13 = -1073741670;
      goto LABEL_61;
    }
    DestinationString.MaximumLength = SourceString.Length;
    RtlCopyUnicodeString(&DestinationString, &SourceString);
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, 0);
  }
  v24 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 130, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0, 0);
    v24 = WPP_GLOBAL_Control;
  }
  v13 = 0;
LABEL_61:
  if ( (*(_DWORD *)(&v24[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(v24[3].Buffer, 19, WPP_9bc989344d36314fcec0e76bff3b0413_Traceguids, (unsigned int)v13, v13);
    v24 = WPP_GLOBAL_Control;
  }
  if ( v13 < 0 )
  {
LABEL_64:
    if ( (*(_DWORD *)(&v24[4].MaximumLength + 1) & 0x20000) == 0 )
      return (unsigned int)v13;
    v30 = 189;
    goto LABEL_160;
  }
  if ( DestinationString.Length )
  {
    *a3 = 1;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 190, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids);
    }
    v13 = SystemFunction025(DestinationString.Buffer, &v65, a2);
  }
  else
  {
    *a3 = 0;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 191, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids);
    }
    *a2 = SampNullLmOwfPassword;
  }
  Length = DestinationString.Length;
  v32 = DestinationString.Buffer;
  if ( DestinationString.Length )
  {
    do
    {
      *(_BYTE *)v32 = 0;
      v32 = (PWSTR)((char *)v32 + 1);
      --Length;
    }
    while ( Length );
  }
  if ( DestinationString.Buffer )
  {
    LocalFree(DestinationString.Buffer);
    DestinationString.Buffer = 0;
  }
  if ( v13 < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return (unsigned int)v13;
    v30 = 192;
    goto LABEL_160;
  }
  if ( (*((_BYTE *)a1 + 192) & 2) == 0 )
  {
    v35 = SampValidateRegAttributes(a1, 1u);
    goto LABEL_93;
  }
  if ( !*((_QWORD *)a1 + 14) )
  {
    v13 = SampValidateDsAttributes(a1, 0);
    if ( v13 < 0 )
      goto LABEL_94;
    goto LABEL_91;
  }
  if ( !_bittest64(*((const signed __int64 **)a1 + 8), 0xEu) )
  {
LABEL_91:
    v35 = SampValidateDsAttributes(a1, 1u);
LABEL_93:
    v13 = v35;
    goto LABEL_94;
  }
  v33 = (void *)*((_QWORD *)a1 + 17);
  if ( v33 )
    LocalFree(v33);
  v34 = *((_QWORD *)a1 + 14);
  *((_BYTE *)a1 + 20) &= 0xF0u;
  *((_QWORD *)a1 + 17) = v34;
  *((_QWORD *)a1 + 14) = 0;
  *((_QWORD *)a1 + 15) = 0;
  *((_DWORD *)a1 + 32) = 0;
  v13 = SampValidateDsAttributes(a1, 0);
  if ( v13 >= 0 )
  {
    v13 = SampValidateDsAttributes(a1, 1u);
    if ( v13 >= 0 )
    {
      SampMarkPerAttributeInvalidFromWhichFields(a1, 0);
      *((_BYTE *)a1 + 29) &= ~1u;
    }
  }
LABEL_94:
  v36 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      110,
      WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
      (unsigned int)v13,
      v13);
    v36 = WPP_GLOBAL_Control;
  }
  if ( v13 < 0 )
  {
    if ( (*(_DWORD *)(&v36[4].MaximumLength + 1) & 0x20000) == 0 )
      return (unsigned int)v13;
    WPP_SF_Dd(v36[3].Buffer, 29, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids, (unsigned int)v13, v13);
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return (unsigned int)v13;
    v37 = WPP_GLOBAL_Control[3].Buffer;
    v30 = 193;
LABEL_161:
    WPP_SF_Dd(v37, v30, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, (unsigned int)v13, v13);
    return (unsigned int)v13;
  }
  v38 = *((_QWORD *)a1 + 14);
  v39 = 88LL * *((int *)a1 + 4);
  if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
  {
    v40 = *(unsigned int *)((char *)&SampObjectInformation + v39 + 76);
    SourceString.MaximumLength = *(_WORD *)(v40 + v38 + 172);
    SourceString.Length = SourceString.MaximumLength;
    v41 = *(_DWORD *)((char *)&SampObjectInformation + v39 + 72);
  }
  else
  {
    v40 = *(unsigned int *)((char *)&SampObjectInformation + v39 + 52);
    SourceString.MaximumLength = *(_WORD *)(v40 + v38 + 172);
    SourceString.Length = SourceString.MaximumLength;
    v41 = *(_DWORD *)((char *)&SampObjectInformation + v39 + 56);
  }
  SourceString.Buffer = (PWSTR)(v38 + (unsigned int)(*(_DWORD *)(v40 + v38 + 168) + v41));
  if ( (*(_DWORD *)(&v36[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v36[3].Buffer, 30, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids, 0, 0);
  v42 = SampIsDataEncrypted(a1, &SourceString);
  if ( SampSecretEncryptionEnabled )
  {
    if ( v42 )
    {
      v44 = SourceString.Buffer;
      v45 = *SourceString.Buffer;
      if ( v45 != SampCurrentPEKID && v45 != SampPreviousPEKID )
      {
        v13 = -1073741595;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
          return (unsigned int)v13;
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          18,
          WPP_9bc989344d36314fcec0e76bff3b0413_Traceguids,
          3221225701LL,
          -1073741595);
        v24 = WPP_GLOBAL_Control;
        goto LABEL_142;
      }
      if ( (SourceString.Buffer[1] & 2) != 0 )
      {
        v46 = SampDecryptSecretDataWithAes(&DestinationString, &SourceString, v43);
        v24 = WPP_GLOBAL_Control;
        v13 = v46;
        goto LABEL_139;
      }
      v63 = v61;
      v70 = 0;
      hKey = 0;
      DestinationString = 0;
      DestinationString.Length = SourceString.Length - 4;
      DestinationString.MaximumLength = SourceString.Length - 4;
      *(_OWORD *)phHash = 0;
      if ( SourceString.Length == 4 )
      {
        DestinationString.Buffer = 0;
        v24 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          v47 = 12;
          v48 = WPP_9bc989344d36314fcec0e76bff3b0413_Traceguids;
LABEL_137:
          WPP_SF_Dd(v24[3].Buffer, v47, v48, 0, 0);
          v24 = WPP_GLOBAL_Control;
          goto LABEL_138;
        }
        goto LABEL_138;
      }
      DestinationString.Buffer = (PWSTR)LocalAlloc(0x40u, (unsigned __int16)(SourceString.Length - 4));
      if ( DestinationString.Buffer )
      {
        v51 = &SampCurrentPEK;
        if ( *v44 != SampCurrentPEKID )
          v51 = &SampPreviousPEK;
        CngRsa32Compat_MD5Init(phHash);
        CngRsa32Compat_MD5Update(phHash, v51, 16);
        CngRsa32Compat_MD5Update(phHash, &v63, 4);
        if ( (v44[1] & 1) != 0 )
        {
          v61 = 0;
          v52 = SampMagicConstantFromDataType(2, &v61);
          CngRsa32Compat_MD5Update(phHash, v52, v61);
        }
        CngRsa32Compat_MD5Final(phHash);
        CngRsa32Compat_rc4_key(&hKey);
        memcpy_0(DestinationString.Buffer, v44 + 2, DestinationString.Length);
        CngRsa32Compat_rc4(&hKey, DestinationString.Length, DestinationString.Buffer);
        BCryptDestroyKey(hKey);
        hKey = 0;
        v24 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
          goto LABEL_138;
        v47 = 14;
        v48 = WPP_9bc989344d36314fcec0e76bff3b0413_Traceguids;
        goto LABEL_137;
      }
      v24 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v49 = 13;
        v50 = WPP_9bc989344d36314fcec0e76bff3b0413_Traceguids;
LABEL_131:
        WPP_SF_Dd(v24[3].Buffer, v49, v50, 3221225626LL, -1073741670);
        v24 = WPP_GLOBAL_Control;
        goto LABEL_132;
      }
      goto LABEL_132;
    }
    if ( (SourceString.Length & 0xF) != 0 )
    {
      v53 = SampDuplicateUnicodeString(&DestinationString, &SampNullString);
      v24 = WPP_GLOBAL_Control;
      v13 = v53;
      goto LABEL_139;
    }
  }
  if ( SourceString.Length )
  {
    DestinationString.Buffer = (PWSTR)LocalAlloc(0x40u, SourceString.Length);
    if ( !DestinationString.Buffer )
    {
      v24 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v49 = 129;
        v50 = WPP_48bf36016493398285a8dbc678e80a21_Traceguids;
        goto LABEL_131;
      }
LABEL_132:
      v13 = -1073741670;
      goto LABEL_139;
    }
    DestinationString.MaximumLength = SourceString.Length;
    RtlCopyUnicodeString(&DestinationString, &SourceString);
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, 0);
  }
  v24 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v47 = 130;
    v48 = WPP_48bf36016493398285a8dbc678e80a21_Traceguids;
    goto LABEL_137;
  }
LABEL_138:
  v13 = 0;
LABEL_139:
  if ( (*(_DWORD *)(&v24[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(v24[3].Buffer, 19, WPP_9bc989344d36314fcec0e76bff3b0413_Traceguids, (unsigned int)v13, v13);
    v24 = WPP_GLOBAL_Control;
  }
  if ( v13 < 0 )
  {
LABEL_142:
    if ( (*(_DWORD *)(&v24[4].MaximumLength + 1) & 0x20000) == 0 )
      return (unsigned int)v13;
    v30 = 194;
    goto LABEL_160;
  }
  if ( DestinationString.Length )
  {
    *v67 = 1;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 195, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids);
    }
    v13 = SystemFunction027(DestinationString.Buffer, &v65, v7);
    if ( v13 >= 0 )
    {
      v54 = SystemFunction031(v7, &SampNullNtOwfPassword);
      *v68 = v54 == 0;
    }
  }
  else
  {
    *v67 = 0;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 196, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids);
    }
    v55 = v68;
    *v7 = SampNullNtOwfPassword;
    *v55 = 0;
  }
  v56 = DestinationString.Length;
  v57 = DestinationString.Buffer;
  if ( DestinationString.Length )
  {
    do
    {
      *(_BYTE *)v57 = 0;
      v57 = (PWSTR)((char *)v57 + 1);
      --v56;
    }
    while ( v56 );
  }
  if ( DestinationString.Buffer )
  {
    LocalFree(DestinationString.Buffer);
    DestinationString.Buffer = 0;
  }
  v24 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v30 = 197;
LABEL_160:
    v37 = v24[3].Buffer;
    goto LABEL_161;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180016d50  push    rbp
0x180016d52  push    rbx
0x180016d53  push    rsi
0x180016d54  push    rdi
0x180016d55  push    r12
0x180016d57  push    r14
0x180016d59  push    r15
0x180016d5b  lea     rbp, [rsp-17h]
0x180016d60  sub     rsp, 0C0h
0x180016d67  mov     rax, cs:__security_cookie
0x180016d6e  xor     rax, rsp
0x180016d71  mov     [rbp+47h+var_50], rax
0x180016d75  test    byte ptr [rcx+0C0h], 2
0x180016d7c  xorps   xmm0, xmm0
0x180016d7f  mov     rax, [rbp+47h+arg_20]
0x180016d83  xorps   xmm1, xmm1
0x180016d86  mov     [rbp+47h+var_78], rax
0x180016d8a  mov     rdi, r9
0x180016d8d  mov     rax, [rbp+47h+arg_28]
0x180016d91  mov     rsi, r8
0x180016d94  mov     [rbp+47h+var_70], rax
0x180016d98  mov     r14, rdx
0x180016d9b  mov     eax, [rcx+0F8h]
0x180016da1  mov     r15, rcx
0x180016da4  mov     [rbp+47h+var_A0], eax
0x180016da7  mov     [rbp+47h+var_84], eax
0x180016daa  mov     [rbp+47h+var_80], r9
0x180016dae  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x180016db2  movups  xmmword ptr [rbp+47h+SourceString.Length], xmm1
0x180016db6  jz      loc_180016E70
0x180016dbc  cmp     qword ptr [rcx+70h], 0
0x180016dc1  jz      loc_180016E54
0x180016dc7  mov     rax, [rcx+40h]
0x180016dcb  bt      qword ptr [rax], 0Dh
0x180016dd0  setb    al
0x180016dd3  test    al, al
0x180016dd5  jz      short loc_180016E48
0x180016dd7  mov     rcx, [rcx+88h]; hMem
0x180016dde  test    rcx, rcx
0x180016de1  jz      short loc_180016DE9
0x180016de3  call    cs:__imp_LocalFree
0x180016de9  mov     rax, [r15+70h]
0x180016ded  xor     edx, edx; unsigned int
0x180016def  and     byte ptr [r15+14h], 0F0h
0x180016df4  mov     rcx, r15; struct _SAMP_OBJECT *
0x180016df7  mov     [r15+88h], rax
0x180016dfe  mov     qword ptr [r15+70h], 0
0x180016e06  mov     qword ptr [r15+78h], 0
0x180016e0e  mov     dword ptr [r15+80h], 0
0x180016e19  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x180016e1e  mov     ebx, eax
0x180016e20  test    eax, eax
0x180016e22  js      short loc_180016E7C
0x180016e24  mov     edx, 1; unsigned int
0x180016e29  mov     rcx, r15; struct _SAMP_OBJECT *
0x180016e2c  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x180016e31  mov     ebx, eax
0x180016e33  test    eax, eax
0x180016e35  js      short loc_180016E7C
0x180016e37  xor     edx, edx
0x180016e39  mov     rcx, r15
0x180016e3c  call    SampMarkPerAttributeInvalidFromWhichFields
0x180016e41  and     byte ptr [r15+1Dh], 0FEh
0x180016e46  jmp     short loc_180016E7C
0x180016e48  mov     edx, 1; unsigned int
0x180016e4d  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x180016e52  jmp     short loc_180016E7A
0x180016e54  xor     edx, edx; unsigned int
0x180016e56  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x180016e5b  mov     ebx, eax
0x180016e5d  test    eax, eax
0x180016e5f  js      short loc_180016E7C
0x180016e61  mov     edx, 1; unsigned int
0x180016e66  mov     rcx, r15; struct _SAMP_OBJECT *
0x180016e69  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x180016e6e  jmp     short loc_180016E7A
0x180016e70  mov     edx, 1; unsigned int
0x180016e75  call    SampValidateRegAttributes
0x180016e7a  mov     ebx, eax
0x180016e7c  mov     r10, cs:WPP_GLOBAL_Control
0x180016e83  test    dword ptr [r10+44h], 20000h
0x180016e8b  jz      short loc_180016EB0
0x180016e8d  mov     rcx, [r10+38h]
0x180016e91  lea     r8, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids
0x180016e98  mov     edx, 6Eh ; 'n'
0x180016e9d  mov     [rsp+0F0h+var_D0], ebx
0x180016ea1  mov     r9d, ebx
0x180016ea4  call    WPP_SF_Dd
0x180016ea9  mov     r10, cs:WPP_GLOBAL_Control
0x180016eb0  test    ebx, ebx
0x180016eb2  jns     short loc_180016F14
0x180016eb4  test    dword ptr [r10+44h], 20000h
0x180016ebc  jz      loc_180017A38
0x180016ec2  mov     rcx, [r10+38h]
0x180016ec6  lea     r8, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids
0x180016ecd  mov     edx, 1Dh
0x180016ed2  mov     [rsp+0F0h+var_D0], ebx
0x180016ed6  mov     r9d, ebx
0x180016ed9  call    WPP_SF_Dd
0x180016ede  mov     r10, cs:WPP_GLOBAL_Control
0x180016ee5  test    dword ptr [r10+44h], 20000h
0x180016eed  jz      loc_180017A38
0x180016ef3  mov     rcx, [r10+38h]
0x180016ef7  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x180016efe  mov     edx, 0BCh
0x180016f03  mov     [rsp+0F0h+var_D0], ebx
0x180016f07  mov     r9d, ebx
0x180016f0a  call    WPP_SF_Dd
0x180016f0f  jmp     loc_180017A38
0x180016f14  movsxd  rax, dword ptr [r15+10h]
0x180016f18  mov     r8, [r15+70h]
0x180016f1c  imul    rdx, rax, 58h ; 'X'
0x180016f20  test    byte ptr [r15+0C0h], 2
0x180016f28  mov     [rsp+0F0h+var_38], r13
0x180016f30  lea     r13, ?SampObjectInformation@@3PAU_SAMP_OBJECT_INFORMATION@@A; _SAMP_OBJECT_INFORMATION near * SampObjectInformation
0x180016f37  jz      short loc_180016F5B
0x180016f39  mov     eax, [rdx+r13+4Ch]
0x180016f3e  movzx   ecx, word ptr [rax+r8+0A0h]
0x180016f47  mov     eax, [rdx+r13+4Ch]
0x180016f4c  mov     [rbp+47h+SourceString.MaximumLength], cx
0x180016f50  mov     [rbp+47h+SourceString.Length], cx
0x180016f54  mov     ecx, [rdx+r13+48h]
0x180016f59  jmp     short loc_180016F7B
0x180016f5b  mov     eax, [rdx+r13+34h]
0x180016f60  movzx   ecx, word ptr [rax+r8+0A0h]
0x180016f69  mov     eax, [rdx+r13+34h]
0x180016f6e  mov     [rbp+47h+SourceString.MaximumLength], cx
0x180016f72  mov     [rbp+47h+SourceString.Length], cx
0x180016f76  mov     ecx, [rdx+r13+38h]
0x180016f7b  add     ecx, [rax+r8+9Ch]
0x180016f83  mov     eax, ecx
0x180016f85  add     rax, r8
0x180016f88  mov     [rbp+47h+SourceString.Buffer], rax
0x180016f8c  test    dword ptr [r10+44h], 20000h
0x180016f94  jz      short loc_180016FB6
0x180016f96  mov     rcx, [r10+38h]
0x180016f9a  lea     r8, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids
0x180016fa1  mov     edx, 1Eh
0x180016fa6  mov     [rsp+0F0h+var_D0], 0
0x180016fae  xor     r9d, r9d
0x180016fb1  call    WPP_SF_Dd
0x180016fb6  lea     rdx, [rbp+47h+SourceString]; struct _UNICODE_STRING *
0x180016fba  mov     rcx, r15; struct _SAMP_OBJECT *
0x180016fbd  call    ?SampIsDataEncrypted@@YAEPEAU_SAMP_OBJECT@@PEAU_UNICODE_STRING@@@Z; SampIsDataEncrypted(_SAMP_OBJECT *,_UNICODE_STRING *)
0x180016fc2  cmp     cs:?SampSecretEncryptionEnabled@@3EA, 0; uchar SampSecretEncryptionEnabled
0x180016fc9  jz      loc_18001722E
0x180016fcf  test    al, al
0x180016fd1  jz      loc_18001720A
0x180016fd7  mov     rdi, [rbp+47h+SourceString.Buffer]
0x180016fdb  movzx   eax, word ptr [rdi]
0x180016fde  cmp     eax, cs:?SampCurrentPEKID@@3KA; ulong SampCurrentPEKID
0x180016fe4  jz      short loc_180017032
0x180016fe6  cmp     eax, cs:?SampPreviousPEKID@@3KA; ulong SampPreviousPEKID
0x180016fec  jz      short loc_180017032
0x180016fee  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ff5  mov     ebx, 0C00000E5h
0x180016ffa  test    dword ptr [rcx+44h], 20000h
0x180017001  jz      loc_180017A30
0x180017007  mov     rcx, [rcx+38h]
0x18001700b  lea     r8, WPP_9bc989344d36314fcec0e76bff3b0413_Traceguids
0x180017012  mov     edx, 12h
0x180017017  mov     [rsp+0F0h+var_D0], ebx
0x18001701b  mov     r9d, 0C00000E5h
0x180017021  call    WPP_SF_Dd
0x180017026  mov     rcx, cs:WPP_GLOBAL_Control
0x18001702d  jmp     loc_18001731B
0x180017032  test    byte ptr [rdi+2], 2
0x180017036  jz      short loc_180017057
0x180017038  lea     rdx, [rbp+47h+SourceString]; struct _UNICODE_STRING *
0x18001703c  lea     rcx, [rbp+47h+DestinationString]; struct _UNICODE_STRING *
0x180017040  call    ?SampDecryptSecretDataWithAes@@YAJPEAU_UNICODE_STRING@@0K@Z; SampDecryptSecretDataWithAes(_UNICODE_STRING *,_UNICODE_STRING *,ulong)
0x180017045  mov     rcx, cs:WPP_GLOBAL_Control
0x18001704c  mov     ebx, eax
0x18001704e  mov     rdi, [rbp+47h+var_80]
0x180017052  jmp     loc_1800172EB
0x180017057  mov     eax, [rbp+47h+var_A0]
0x18001705a  xorps   xmm0, xmm0
0x18001705d  mov     [rbp+47h+var_90], eax
0x180017060  xor     eax, eax
0x180017062  mov     [rbp+47h+var_58], rax
0x180017066  movzx   eax, [rbp+47h+SourceString.Length]
0x18001706a  sub     ax, 4
0x18001706e  mov     [rbp+47h+hKey], 0
0x180017076  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x18001707a  mov     [rbp+47h+DestinationString.Length], ax
0x18001707e  mov     [rbp+47h+DestinationString.MaximumLength], ax
0x180017082  movups  xmmword ptr [rbp+47h+phHash], xmm0
0x180017086  jnz     short loc_1800170AE
0x180017088  mov     [rbp+47h+DestinationString.Buffer], 0
0x180017090  mov     rcx, cs:WPP_GLOBAL_Control
0x180017097  test    dword ptr [rcx+44h], 20000h
0x18001709e  jz      loc_1800171FF
0x1800170a4  mov     edx, 0Ch
0x1800170a9  jmp     loc_1800171DD
0x1800170ae  movzx   edx, ax; uBytes
0x1800170b1  mov     ecx, 40h ; '@'; uFlags
0x1800170b6  call    cs:__imp_LocalAlloc
0x1800170bc  mov     [rbp+47h+DestinationString.Buffer], rax
0x1800170c0  test    rax, rax
0x1800170c3  jnz     short loc_180017109
0x1800170c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170cc  test    dword ptr [rcx+44h], 20000h
0x1800170d3  jz      short loc_1800170FF
0x1800170d5  mov     rcx, [rcx+38h]
0x1800170d9  lea     r8, WPP_9bc989344d36314fcec0e76bff3b0413_Traceguids
0x1800170e0  mov     edx, 0Dh
0x1800170e5  mov     [rsp+0F0h+var_D0], 0C000009Ah
0x1800170ed  mov     r9d, 0C000009Ah
0x1800170f3  call    WPP_SF_Dd
0x1800170f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170ff  mov     ebx, 0C000009Ah
0x180017104  jmp     loc_180017201
0x180017109  movzx   eax, word ptr [rdi]
0x18001710c  lea     rbx, ?SampCurrentPEK@@3PAEA; uchar near * SampCurrentPEK
0x180017113  cmp     eax, cs:?SampCurrentPEKID@@3KA; ulong SampCurrentPEKID
0x180017119  lea     rcx, [rbp+47h+phHash]; phHash
0x18001711d  lea     rax, ?SampPreviousPEK@@3PAEA; uchar near * SampPreviousPEK
0x180017124  cmovnz  rbx, rax
0x180017128  call    CngRsa32Compat_MD5Init
0x18001712d  mov     r8d, 10h
0x180017133  lea     rcx, [rbp+47h+phHash]
0x180017137  mov     rdx, rbx
0x18001713a  call    CngRsa32Compat_MD5Update
0x18001713f  mov     r8d, 4
0x180017145  lea     rdx, [rbp+47h+var_90]
0x180017149  lea     rcx, [rbp+47h+phHash]
0x18001714d  call    CngRsa32Compat_MD5Update
0x180017152  test    byte ptr [rdi+2], 1
0x180017156  jz      short loc_18001717D
0x180017158  lea     rdx, [rbp+47h+var_88]
0x18001715c  mov     [rbp+47h+var_88], 0
0x180017163  mov     ecx, 1
0x180017168  call    ?SampMagicConstantFromDataType@@YAPEAEW4_SAMP_ENCRYPTED_DATA_TYPE@@PEAK@Z; SampMagicConstantFromDataType(_SAMP_ENCRYPTED_DATA_TYPE,ulong *)
0x18001716d  mov     r8d, [rbp+47h+var_88]
0x180017171  lea     rcx, [rbp+47h+phHash]
0x180017175  mov     rdx, rax
0x180017178  call    CngRsa32Compat_MD5Update
0x18001717d  lea     rcx, [rbp+47h+phHash]
0x180017181  call    CngRsa32Compat_MD5Final
0x180017186  lea     r8, [rbp+47h+phHash+8]
0x18001718a  lea     rcx, [rbp+47h+hKey]; phKey
0x18001718e  call    CngRsa32Compat_rc4_key
0x180017193  movzx   r8d, [rbp+47h+DestinationString.Length]; Size
0x180017198  lea     rdx, [rdi+4]; Src
0x18001719c  mov     rcx, [rbp+47h+DestinationString.Buffer]; void *
0x1800171a0  call    memcpy_0
0x1800171a5  movzx   edx, [rbp+47h+DestinationString.Length]
0x1800171a9  lea     rcx, [rbp+47h+hKey]
0x1800171ad  mov     r8, [rbp+47h+DestinationString.Buffer]
0x1800171b1  call    CngRsa32Compat_rc4
0x1800171b6  mov     rcx, [rbp+47h+hKey]; hKey
0x1800171ba  call    cs:__imp_BCryptDestroyKey
0x1800171c0  mov     [rbp+47h+hKey], 0
0x1800171c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171cf  test    dword ptr [rcx+44h], 20000h
0x1800171d6  jz      short loc_1800171FF
0x1800171d8  mov     edx, 0Eh
0x1800171dd  mov     rcx, [rcx+38h]
0x1800171e1  lea     r8, WPP_9bc989344d36314fcec0e76bff3b0413_Traceguids
0x1800171e8  xor     r9d, r9d
0x1800171eb  mov     [rsp+0F0h+var_D0], 0
0x1800171f3  call    WPP_SF_Dd
0x1800171f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171ff  xor     ebx, ebx
0x180017201  mov     rdi, [rbp+47h+var_80]
0x180017205  jmp     loc_1800172EB
0x18001720a  test    byte ptr [rbp+47h+SourceString.Length], 0Fh
0x18001720e  jz      short loc_18001722E
0x180017210  lea     rdx, ?SampNullString@@3U_UNICODE_STRING@@A; SourceString
0x180017217  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x18001721b  call    SampDuplicateUnicodeString
0x180017220  mov     rcx, cs:WPP_GLOBAL_Control
0x180017227  mov     ebx, eax
0x180017229  jmp     loc_1800172EB
0x18001722e  movzx   eax, [rbp+47h+SourceString.Length]
0x180017232  test    ax, ax
0x180017235  jz      short loc_1800172A6
0x180017237  mov     edx, eax; uBytes
0x180017239  mov     ecx, 40h ; '@'; uFlags
0x18001723e  call    cs:__imp_LocalAlloc
0x180017244  mov     [rbp+47h+DestinationString.Buffer], rax
0x180017248  test    rax, rax
0x18001724b  jnz     short loc_18001728E
0x18001724d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017254  test    dword ptr [rcx+44h], 20000h
0x18001725b  jz      short loc_180017287
0x18001725d  mov     rcx, [rcx+38h]
0x180017261  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180017268  mov     edx, 81h
0x18001726d  mov     [rsp+0F0h+var_D0], 0C000009Ah
0x180017275  mov     r9d, 0C000009Ah
0x18001727b  call    WPP_SF_Dd
0x180017280  mov     rcx, cs:WPP_GLOBAL_Control
0x180017287  mov     ebx, 0C000009Ah
0x18001728c  jmp     short loc_1800172EB
0x18001728e  movzx   eax, [rbp+47h+SourceString.Length]
0x180017292  lea     rdx, [rbp+47h+SourceString]; SourceString
0x180017296  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x18001729a  mov     [rbp+47h+DestinationString.MaximumLength], ax
0x18001729e  call    cs:__imp_RtlCopyUnicodeString
  ... truncated ...
```
