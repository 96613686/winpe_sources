# ChannelConfigWriter::Validate(bool)

- ea: `0x180084f98`
- end: `0x18008697a`
- name: `?Validate@ChannelConfigWriter@@QEAAX_N@Z`
- size: `6626`
- prototype: `void __fastcall(ChannelConfigWriter *__hidden this, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800840c8`

## callees

- `0x180009260`
- `0x18000a180`
- `0x18003ee78`
- `0x180047fd8`
- `0x18006c144`
- `0x180084f98`
- `0x180086980`
- `0x180086a28`
- `0x180092008`
- `0x18009e81c`
- `0x1800c0dd0`
- `0x1800c12e0`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008577c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008577c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008576e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008576e`

## string_xrefs

- `0x18008505f`: `ChannelConfigException`
- `0x180085104`: `ChannelConfigException`
- `0x1800851a7`: `ChannelConfigException`
- `0x1800852ac`: `ChannelConfigException`
- `0x180085342`: `ChannelConfigException`
- `0x1800853ef`: `ChannelConfigException`
- `0x18008553b`: `ChannelConfigException`
- `0x1800855cd`: `ChannelConfigException`
- `0x1800857d0`: `ChannelConfigException`
- `0x1800858a4`: `ChannelConfigException`
- `0x1800859c7`: `ChannelConfigException`
- `0x180085a77`: `ChannelConfigException`
- `0x180085cae`: `ChannelConfigException`
- `0x180085d48`: `ChannelConfigException`
- `0x180085e79`: `ChannelConfigException`
- `0x180085faa`: `ChannelConfigException`
- `0x180086051`: `ChannelConfigException`
- `0x180086101`: `ChannelConfigException`
- `0x180086224`: `ChannelConfigException`
- `0x180086347`: `ChannelConfigException`
- `0x180086468`: `ChannelConfigException`
- `0x18008658e`: `ChannelConfigException`
- `0x18008663b`: `ChannelConfigException`
- `0x18008675e`: `ChannelConfigException`
- `0x18008680b`: `ChannelConfigException`
- `0x180086915`: `ChannelConfigException`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall ChannelConfigWriter::Validate(ChannelConfigWriter *this, char a2)
{
  char v3; // al
  char v4; // r13
  char v5; // cl
  char v6; // r12
  char v7; // al
  ULONG v8; // r15d
  char v9; // al
  enum _EVT_CHANNEL_ISOLATION_TYPE CurrentIsolation; // edi
  bool CurrentEnabledValue; // al
  int v12; // r9d
  char v13; // dl
  int v14; // ecx
  __int64 v15; // rdx
  char DefaultEnabledValueForChannel; // di
  char v17; // r15
  bool v18; // zf
  char v19; // di
  PSECURITY_DESCRIPTOR *v20; // rax
  DWORD LastError; // ebx
  char v22; // cl
  _BYTE *v23; // rax
  __int64 v24; // [rsp+38h] [rbp-29h] BYREF
  __int64 v25; // [rsp+40h] [rbp-21h]
  __int128 v26; // [rsp+48h] [rbp-19h] BYREF
  __int64 v27; // [rsp+58h] [rbp-9h]
  int v28; // [rsp+60h] [rbp-1h]
  int v29; // [rsp+64h] [rbp+3h]
  int v30; // [rsp+68h] [rbp+7h]
  __int128 pExceptionObject; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v32; // [rsp+80h] [rbp+1Fh]
  int v33; // [rsp+88h] [rbp+27h]
  int v34; // [rsp+8Ch] [rbp+2Bh]
  int v35; // [rsp+90h] [rbp+2Fh]
  __int64 v36; // [rsp+C8h] [rbp+67h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+D0h] [rbp+6Fh] BYREF

  LOBYTE(SecurityDescriptorSize) = a2;
  v24 = *((_QWORD *)this + 35);
  v25 = (*((_QWORD *)this + 36) - v24) >> 1;
  v3 = IsCoreChannel(&v24);
  v4 = v3;
  v5 = *((_BYTE *)this + 352);
  if ( v5 != 1 || (v6 = 1, v3) )
    v6 = 0;
  if ( (*((_BYTE *)this + 236) & 3) != 0 )
  {
    *(_QWORD *)&v26 = 0;
    v27 = 0x400003AAFLL;
    v28 = 87;
    v29 = -1;
    v30 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
        (unsigned int)"ChannelConfigException",
        87);
    }
    pExceptionObject = 0;
    v32 = 0x400003AAFLL;
    v33 = 87;
    v34 = -1;
    v35 = 0;
    *((_QWORD *)&v26 + 1) = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 235) & 3) != 0 )
  {
    *(_QWORD *)&pExceptionObject = 0;
    v32 = 0x300003AAFLL;
    v33 = 87;
    v34 = -1;
    v35 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
        (unsigned int)"ChannelConfigException",
        87);
    }
    v26 = 0;
    v27 = 0x300003AAFLL;
    v28 = 87;
    v29 = -1;
    v30 = 0;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    throw (ChannelConfigException *)&v26;
  }
  v7 = *((_BYTE *)this + 234);
  if ( (v7 & 1) != 0 )
  {
    *(_QWORD *)&pExceptionObject = 0;
    v32 = 0x200003AAFLL;
    v33 = 87;
    v34 = -1;
    v35 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
        (unsigned int)"ChannelConfigException",
        87);
    }
    v26 = 0;
    v27 = 0x200003AAFLL;
    v28 = 87;
    v29 = -1;
    v30 = 0;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    throw (ChannelConfigException *)&v26;
  }
  if ( (v7 & 2) != 0 )
  {
    *(_QWORD *)&pExceptionObject = 0;
    v32 = 0x200003AAFLL;
    v33 = 87;
    v34 = -1;
    v35 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
        (unsigned int)"ChannelConfigException",
        87);
    }
    v26 = 0;
    v27 = 0x200003AAFLL;
    v28 = 87;
    v29 = -1;
    v30 = 0;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    throw (ChannelConfigException *)&v26;
  }
  if ( v5 == 1 )
  {
    v8 = 0;
  }
  else
  {
    SecurityDescriptorSize = 0;
    v8 = 1;
    if ( !(unsigned int)RegReadDWORDValueNoThrow(*((HKEY *)this + 32), 0, L"Type", &SecurityDescriptorSize) )
      v8 = SecurityDescriptorSize;
  }
  v9 = *((_BYTE *)this + 233);
  if ( (v9 & 1) != 0 )
  {
    if ( v6 || v4 )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x100003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x100003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    CurrentIsolation = *((_DWORD *)this + 13);
    if ( (unsigned int)CurrentIsolation > EvtChannelIsolationTypeCustom )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x100003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x100003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
  }
  else
  {
    if ( (v9 & 2) != 0 && (v6 || v4) )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x100003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x100003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    CurrentIsolation = ChannelConfigWriter::GetCurrentIsolation(this);
  }
  CurrentEnabledValue = ChannelConfigWriter::GetCurrentEnabledValue(this);
  v13 = CurrentEnabledValue;
  LOBYTE(SecurityDescriptorSize) = CurrentEnabledValue;
  LOBYTE(v14) = *((_BYTE *)this + 232);
  if ( (v14 & 3) != 0 )
  {
    v15 = 0;
    if ( v6 || v4 )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 15023;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 15023;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( (v14 & 2) != 0 )
    {
      v24 = *((_QWORD *)this + 35);
      v25 = (*((_QWORD *)this + 36) - v24) >> 1;
      LOBYTE(v15) = *((_BYTE *)this + 352);
      DefaultEnabledValueForChannel = ChannelConfigSnapshot::GetDefaultEnabledValueForChannel(
                                        &v24,
                                        v15,
                                        (unsigned int)CurrentIsolation);
    }
    else
    {
      DefaultEnabledValueForChannel = *((_BYTE *)this + 56);
    }
    if ( (Microsoft_Windows_EventlogEnableBits & 0x400) != 0 )
    {
      LOBYTE(v12) = *((_BYTE *)this + 48);
      McTemplateU0zut_EventWriteTransfer(v14, v15, *((_QWORD *)this + 35), v12, DefaultEnabledValueForChannel);
    }
    if ( DefaultEnabledValueForChannel && (unsigned __int8)AreAnyRestrictionsEnabled(16) )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 15023;
      v33 = 50;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          50);
      }
      v26 = 0;
      v27 = 15023;
      v28 = 50;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    v13 = SecurityDescriptorSize;
  }
  else
  {
    DefaultEnabledValueForChannel = CurrentEnabledValue;
  }
  if ( v8 - 2 > 1 )
  {
    v17 = 0;
LABEL_76:
    v19 = 0;
    goto LABEL_77;
  }
  v17 = 1;
  if ( !v13 )
    goto LABEL_76;
  v18 = DefaultEnabledValueForChannel == 0;
  v19 = 1;
  if ( v18 )
    goto LABEL_76;
LABEL_77:
  if ( (*((_BYTE *)this + 233) & 3) != 0 && v19 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
    }
    pExceptionObject = 0;
    v32 = 0;
    v33 = 15022;
    v34 = -1;
    v35 = 433;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 237) & 3) != 0 )
  {
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
      }
      pExceptionObject = 0;
      v32 = 0;
      v33 = 15022;
      v34 = -1;
      v35 = 447;
      throw (EvtException *)&pExceptionObject;
    }
    if ( *((_QWORD *)this + 2) != *((_QWORD *)this + 3) )
    {
      v36 = 0;
      SecurityDescriptorSize = 0;
      v20 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v36);
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
              *((LPCWSTR *)this + 2),
              1u,
              v20,
              &SecurityDescriptorSize) )
      {
        LastError = GetLastError();
        *(_QWORD *)&pExceptionObject = 0;
        v32 = 0x500003AAFLL;
        v33 = LastError;
        v34 = -1;
        v35 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
            (unsigned int)"ChannelConfigException",
            LastError);
        }
        v26 = 0;
        v27 = 0x500003AAFLL;
        v28 = LastError;
        v29 = -1;
        v30 = 0;
        *((_QWORD *)&pExceptionObject + 1) = 0;
        throw (ChannelConfigException *)&v26;
      }
      tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v36);
    }
  }
  v22 = *((_BYTE *)this + 238);
  v23 = (char *)this + 224;
  if ( (v22 & 3) != 0 )
  {
    if ( (!*v23 || (v22 & 2) != 0) && *((_BYTE *)this + 225) )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x600003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x600003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
      }
      pExceptionObject = 0;
      v32 = 0;
      v33 = 15022;
      v34 = -1;
      v35 = 493;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( (*((_BYTE *)this + 239) & 3) != 0 )
  {
    if ( v17 )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x700003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x700003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( !*v23 && *((_BYTE *)this + 225) )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x700003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x700003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
  }
  if ( (*((_BYTE *)this + 240) & 3) != 0 && v19 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
    }
    pExceptionObject = 0;
    v32 = 0;
    v33 = 15022;
    v34 = -1;
    v35 = 530;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 241) & 3) != 0 && v19 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
    }
    pExceptionObject = 0;
    v32 = 0;
    v33 = 15022;
    v34 = -1;
    v35 = 550;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 252) & 1) != 0 )
  {
    if ( v4 || v6 || !v17 )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x1400003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x1400003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
      }
      pExceptionObject = 0;
      v32 = 0;
      v33 = 15022;
      v34 = -1;
      v35 = 567;
      throw (EvtException *)&pExceptionObject;
    }
    if ( *((_DWORD *)this + 26) > 0x10u )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x1400003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x1400003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
  }
  if ( (*((_BYTE *)this + 242) & 3) != 0 )
  {
    if ( v4 || v6 || !v17 )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0xA00003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0xA00003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
      }
      pExceptionObject = 0;
      v32 = 0;
      v33 = 15022;
      v34 = -1;
      v35 = 589;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( (*((_BYTE *)this + 243) & 3) != 0 )
  {
    if ( v4 || v6 || !v17 )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0xB00003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0xB00003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
      }
      pExceptionObject = 0;
      v32 = 0;
      v33 = 15022;
      v34 = -1;
      v35 = 606;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( (*((_BYTE *)this + 244) & 3) != 0 )
  {
    *(_QWORD *)&pExceptionObject = 0;
    v32 = 0xC00003AAFLL;
    v33 = 87;
    v34 = -1;
    v35 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
        (unsigned int)"ChannelConfigException",
        87);
    }
    v26 = 0;
    v27 = 0xC00003AAFLL;
    v28 = 87;
    v29 = -1;
    v30 = 0;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    throw (ChannelConfigException *)&v26;
  }
  if ( (*((_BYTE *)this + 245) & 3) != 0 )
  {
    if ( !v17 )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0xD00003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0xD00003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
      }
      pExceptionObject = 0;
      v32 = 0;
      v33 = 15022;
      v34 = -1;
      v35 = 640;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( (*((_BYTE *)this + 246) & 3) != 0 )
  {
    if ( !v17 )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0xE00003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0xE00003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
      }
      pExceptionObject = 0;
      v32 = 0;
      v33 = 15022;
      v34 = -1;
      v35 = 657;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( (*((_BYTE *)this + 247) & 3) != 0 )
  {
    if ( !v17 )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0xF00003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0xF00003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
      }
      pExceptionObject = 0;
      v32 = 0;
      v33 = 15022;
      v34 = -1;
      v35 = 674;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( (*((_BYTE *)this + 248) & 3) != 0 )
  {
    if ( !v17 )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x1000003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x1000003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
      }
      pExceptionObject = 0;
      v32 = 0;
      v33 = 15022;
      v34 = -1;
      v35 = 691;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( (*((_BYTE *)this + 249) & 3) != 0 )
  {
    if ( !v17 )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x1100003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          63,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x1100003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( *((_BYTE *)this + 112) >= 2u )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x1100003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x1100003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
      }
      pExceptionObject = 0;
      v32 = 0;
      v33 = 15022;
      v34 = -1;
      v35 = 714;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( (*((_BYTE *)this + 250) & 3) != 0 )
  {
    if ( !v17 )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x1200003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x1200003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( *((_BYTE *)this + 113) >= 2u )
    {
      *(_QWORD *)&pExceptionObject = 0;
      v32 = 0x1200003AAFLL;
      v33 = 87;
      v34 = -1;
      v35 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          (unsigned int)&WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
          (unsigned int)"ChannelConfigException",
          87);
      }
      v26 = 0;
      v27 = 0x1200003AAFLL;
      v28 = 87;
      v29 = -1;
      v30 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      throw (ChannelConfigException *)&v26;
    }
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 15022);
      }
      pExceptionObject = 0;
      v32 = 0;
      v33 = 15022;
      v34 = -1;
      v35 = 737;
      throw (EvtException *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180084f98  mov     rax, rsp
0x180084f9b  mov     [rax+18h], rbx
0x180084f9f  mov     [rax+20h], rsi
0x180084fa3  mov     [rax+10h], dl
0x180084fa6  push    rbp
0x180084fa7  push    rdi
0x180084fa8  push    r12
0x180084faa  push    r13
0x180084fac  push    r15
0x180084fae  lea     rbp, [rax-5Fh]
0x180084fb2  sub     rsp, 90h
0x180084fb9  mov     rbx, rcx
0x180084fbc  mov     rax, [rcx+118h]
0x180084fc3  mov     [rbp+57h+var_80], rax
0x180084fc7  mov     rdx, [rcx+120h]
0x180084fce  sub     rdx, rax
0x180084fd1  sar     rdx, 1
0x180084fd4  mov     [rbp+57h+var_78], rdx
0x180084fd8  lea     rcx, [rbp+57h+var_80]
0x180084fdc  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180084fe1  mov     r13b, al
0x180084fe4  mov     cl, [rbx+160h]
0x180084fea  xor     edx, edx; wchar_t *
0x180084fec  lea     r8d, [rdx+1]
0x180084ff0  cmp     cl, r8b
0x180084ff3  jnz     short loc_180084FFC
0x180084ff5  test    al, al
0x180084ff7  mov     r12b, r8b
0x180084ffa  jz      short loc_180084FFF
0x180084ffc  mov     r12b, dl
0x180084fff  mov     r15d, 3
0x180085005  test    [rbx+0ECh], r15b
0x18008500c  jz      loc_1800850AC
0x180085012  mov     qword ptr [rbp+57h+var_70], rdx
0x180085016  mov     edi, 3AAFh
0x18008501b  mov     dword ptr [rbp+57h+var_60], edi
0x18008501e  mov     dword ptr [rbp+57h+var_60+4], 4
0x180085025  lea     ebx, [r15+54h]
0x180085029  mov     [rbp+57h+var_58], ebx
0x18008502c  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x180085033  mov     [rbp+57h+var_50], edx
0x180085036  lea     rax, WPP_GLOBAL_Control
0x18008503d  mov     rcx, cs:WPP_GLOBAL_Control
0x180085044  cmp     rcx, rax
0x180085047  jz      short loc_180085078
0x180085049  test    byte ptr [rcx+1Ch], 4
0x18008504d  jz      short loc_180085078
0x18008504f  lea     esi, [rbx-55h]
0x180085052  cmp     [rcx+19h], sil
0x180085056  jb      short loc_180085078
0x180085058  lea     edx, [rbx-3Fh]
0x18008505b  mov     [rsp+0B0h+var_90], ebx
0x18008505f  lea     r9, aChannelconfige; "ChannelConfigException"
0x180085066  lea     r8, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids
0x18008506d  mov     rcx, [rcx+10h]
0x180085071  call    WPP_SF_sD
0x180085076  xor     edx, edx
0x180085078  xorps   xmm0, xmm0
0x18008507b  movdqu  [rbp+57h+pExceptionObject], xmm0
0x180085080  mov     dword ptr [rbp+57h+var_38], edi
0x180085083  mov     dword ptr [rbp+57h+var_38+4], 4
0x18008508a  mov     [rbp+57h+var_30], ebx
0x18008508d  mov     [rbp+57h+var_2C], 0FFFFFFFFh
0x180085094  mov     [rbp+57h+var_28], edx
0x180085097  mov     qword ptr [rbp+57h+var_70+8], rdx
0x18008509b  lea     rdx, _TI2?AVChannelConfigException@@; pThrowInfo
0x1800850a2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800850a6  call    _CxxThrowException_0
0x1800850ac  test    [rbx+0EBh], r15b
0x1800850b3  jz      loc_18008514E
0x1800850b9  mov     qword ptr [rbp+57h+pExceptionObject], rdx
0x1800850bd  mov     edi, 3AAFh
0x1800850c2  mov     dword ptr [rbp+57h+var_38], edi
0x1800850c5  mov     dword ptr [rbp+57h+var_38+4], r15d
0x1800850c9  mov     ebx, 57h ; 'W'
0x1800850ce  mov     [rbp+57h+var_30], ebx
0x1800850d1  mov     [rbp+57h+var_2C], 0FFFFFFFFh
0x1800850d8  mov     [rbp+57h+var_28], edx
0x1800850db  lea     rax, WPP_GLOBAL_Control
0x1800850e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800850e9  cmp     rcx, rax
0x1800850ec  jz      short loc_18008511D
0x1800850ee  test    byte ptr [rcx+1Ch], 4
0x1800850f2  jz      short loc_18008511D
0x1800850f4  lea     esi, [rbx-55h]
0x1800850f7  cmp     [rcx+19h], sil
0x1800850fb  jb      short loc_18008511D
0x1800850fd  lea     edx, [rbx-3Eh]
0x180085100  mov     [rsp+0B0h+var_90], ebx
0x180085104  lea     r9, aChannelconfige; "ChannelConfigException"
0x18008510b  lea     r8, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids
0x180085112  mov     rcx, [rcx+10h]
0x180085116  call    WPP_SF_sD
0x18008511b  xor     edx, edx
0x18008511d  xorps   xmm0, xmm0
0x180085120  movdqu  [rbp+57h+var_70], xmm0
0x180085125  mov     dword ptr [rbp+57h+var_60], edi
0x180085128  mov     dword ptr [rbp+57h+var_60+4], r15d
0x18008512c  mov     [rbp+57h+var_58], ebx
0x18008512f  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x180085136  mov     [rbp+57h+var_50], edx
0x180085139  mov     qword ptr [rbp+57h+pExceptionObject+8], rdx
0x18008513d  lea     rdx, _TI2?AVChannelConfigException@@; pThrowInfo
0x180085144  lea     rcx, [rbp+57h+var_70]; pExceptionObject
0x180085148  call    _CxxThrowException_0
0x18008514e  mov     al, [rbx+0EAh]
0x180085154  mov     esi, 2
0x180085159  test    r8b, al
0x18008515c  jz      loc_1800851F0
0x180085162  mov     qword ptr [rbp+57h+pExceptionObject], rdx
0x180085166  mov     edi, 3AAFh
0x18008516b  mov     dword ptr [rbp+57h+var_38], edi
0x18008516e  mov     dword ptr [rbp+57h+var_38+4], esi
0x180085171  lea     ebx, [rsi+55h]
0x180085174  mov     [rbp+57h+var_30], ebx
0x180085177  mov     [rbp+57h+var_2C], 0FFFFFFFFh
0x18008517e  mov     [rbp+57h+var_28], edx
0x180085181  lea     rax, WPP_GLOBAL_Control
0x180085188  mov     rcx, cs:WPP_GLOBAL_Control
0x18008518f  cmp     rcx, rax
0x180085192  jz      short loc_1800851C0
0x180085194  test    byte ptr [rcx+1Ch], 4
0x180085198  jz      short loc_1800851C0
0x18008519a  cmp     [rcx+19h], sil
0x18008519e  jb      short loc_1800851C0
0x1800851a0  lea     edx, [rsi+19h]
0x1800851a3  mov     [rsp+0B0h+var_90], ebx
0x1800851a7  lea     r9, aChannelconfige; "ChannelConfigException"
0x1800851ae  lea     r8, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids
0x1800851b5  mov     rcx, [rcx+10h]
0x1800851b9  call    WPP_SF_sD
0x1800851be  xor     edx, edx
0x1800851c0  xorps   xmm0, xmm0
0x1800851c3  movdqu  [rbp+57h+var_70], xmm0
0x1800851c8  mov     dword ptr [rbp+57h+var_60], edi
0x1800851cb  mov     dword ptr [rbp+57h+var_60+4], esi
0x1800851ce  mov     [rbp+57h+var_58], ebx
0x1800851d1  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x1800851d8  mov     [rbp+57h+var_50], edx
0x1800851db  mov     qword ptr [rbp+57h+pExceptionObject+8], rdx
0x1800851df  lea     rdx, _TI2?AVChannelConfigException@@; pThrowInfo
0x1800851e6  lea     rcx, [rbp+57h+var_70]; pExceptionObject
0x1800851ea  call    _CxxThrowException_0
0x1800851f0  test    sil, al
0x1800851f3  jnz     loc_1800868CE
0x1800851f9  cmp     cl, r8b
0x1800851fc  jnz     short loc_180085203
0x1800851fe  mov     r15d, edx
0x180085201  jmp     short loc_18008522F
0x180085203  mov     [rbp+57h+SecurityDescriptorSize], edx
0x180085206  lea     r9, [rbp+57h+SecurityDescriptorSize]; unsigned int *
0x18008520a  lea     r8, aType; "Type"
0x180085211  mov     rcx, [rbx+100h]; HKEY
0x180085218  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x18008521d  mov     r8d, 1
0x180085223  mov     r15d, r8d
0x180085226  xor     edx, edx
0x180085228  test    eax, eax
0x18008522a  cmovz   r15d, [rbp+57h+SecurityDescriptorSize]
0x18008522f  mov     al, [rbx+0E9h]
0x180085235  test    r8b, al
0x180085238  jz      loc_180085390
0x18008523e  test    r12b, r12b
0x180085241  jnz     loc_1800852FA
0x180085247  test    r13b, r13b
0x18008524a  jnz     loc_1800852FA
0x180085250  mov     edi, [rbx+34h]
0x180085253  cmp     edi, r8d
0x180085256  jbe     loc_180085447
0x18008525c  cmp     edi, esi
0x18008525e  jz      loc_180085447
0x180085264  mov     qword ptr [rbp+57h+pExceptionObject], rdx
0x180085268  mov     edi, 3AAFh
0x18008526d  mov     dword ptr [rbp+57h+var_38], edi
0x180085270  mov     dword ptr [rbp+57h+var_38+4], r8d
0x180085274  mov     ebx, 57h ; 'W'
0x180085279  mov     [rbp+57h+var_30], ebx
0x18008527c  mov     [rbp+57h+var_2C], 0FFFFFFFFh
0x180085283  mov     [rbp+57h+var_28], edx
0x180085286  lea     rax, WPP_GLOBAL_Control
0x18008528d  mov     rcx, cs:WPP_GLOBAL_Control
0x180085294  cmp     rcx, rax
0x180085297  jz      short loc_1800852C9
0x180085299  test    byte ptr [rcx+1Ch], 4
0x18008529d  jz      short loc_1800852C9
0x18008529f  cmp     [rcx+19h], sil
0x1800852a3  jb      short loc_1800852C9
0x1800852a5  lea     edx, [rbx-39h]
0x1800852a8  mov     [rsp+0B0h+var_90], ebx
0x1800852ac  lea     r9, aChannelconfige; "ChannelConfigException"
0x1800852b3  lea     r8, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids
0x1800852ba  mov     rcx, [rcx+10h]
0x1800852be  call    WPP_SF_sD
0x1800852c3  xor     edx, edx
0x1800852c5  lea     r8d, [rbx-56h]
0x1800852c9  xorps   xmm0, xmm0
0x1800852cc  movdqu  [rbp+57h+var_70], xmm0
0x1800852d1  mov     dword ptr [rbp+57h+var_60], edi
0x1800852d4  mov     dword ptr [rbp+57h+var_60+4], r8d
0x1800852d8  mov     [rbp+57h+var_58], ebx
0x1800852db  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x1800852e2  mov     [rbp+57h+var_50], edx
0x1800852e5  mov     qword ptr [rbp+57h+pExceptionObject+8], rdx
0x1800852e9  lea     rdx, _TI2?AVChannelConfigException@@; pThrowInfo
0x1800852f0  lea     rcx, [rbp+57h+var_70]; pExceptionObject
0x1800852f4  call    _CxxThrowException_0
0x1800852fa  mov     qword ptr [rbp+57h+pExceptionObject], rdx
0x1800852fe  mov     edi, 3AAFh
0x180085303  mov     dword ptr [rbp+57h+var_38], edi
0x180085306  mov     dword ptr [rbp+57h+var_38+4], r8d
0x18008530a  mov     ebx, 57h ; 'W'
0x18008530f  mov     [rbp+57h+var_30], ebx
0x180085312  mov     [rbp+57h+var_2C], 0FFFFFFFFh
0x180085319  mov     [rbp+57h+var_28], edx
0x18008531c  lea     rax, WPP_GLOBAL_Control
0x180085323  mov     rcx, cs:WPP_GLOBAL_Control
0x18008532a  cmp     rcx, rax
0x18008532d  jz      short loc_18008535F
0x18008532f  test    byte ptr [rcx+1Ch], 4
0x180085333  jz      short loc_18008535F
0x180085335  cmp     [rcx+19h], sil
0x180085339  jb      short loc_18008535F
0x18008533b  lea     edx, [rbx-3Ah]
0x18008533e  mov     [rsp+0B0h+var_90], ebx
0x180085342  lea     r9, aChannelconfige; "ChannelConfigException"
0x180085349  lea     r8, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids
0x180085350  mov     rcx, [rcx+10h]
0x180085354  call    WPP_SF_sD
0x180085359  xor     edx, edx
0x18008535b  lea     r8d, [rbx-56h]
0x18008535f  xorps   xmm0, xmm0
0x180085362  movdqu  [rbp+57h+var_70], xmm0
0x180085367  mov     dword ptr [rbp+57h+var_60], edi
0x18008536a  mov     dword ptr [rbp+57h+var_60+4], r8d
0x18008536e  mov     [rbp+57h+var_58], ebx
0x180085371  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x180085378  mov     [rbp+57h+var_50], edx
0x18008537b  mov     qword ptr [rbp+57h+pExceptionObject+8], rdx
0x18008537f  lea     rdx, _TI2?AVChannelConfigException@@; pThrowInfo
0x180085386  lea     rcx, [rbp+57h+var_70]; pExceptionObject
0x18008538a  call    _CxxThrowException_0
0x180085390  test    sil, al
0x180085393  jz      loc_18008543D
0x180085399  test    r12b, r12b
0x18008539c  jnz     short loc_1800853A7
0x18008539e  test    r13b, r13b
0x1800853a1  jz      loc_18008543D
0x1800853a7  mov     qword ptr [rbp+57h+pExceptionObject], rdx
0x1800853ab  mov     edi, 3AAFh
0x1800853b0  mov     dword ptr [rbp+57h+var_38], edi
0x1800853b3  mov     dword ptr [rbp+57h+var_38+4], r8d
0x1800853b7  mov     ebx, 57h ; 'W'
0x1800853bc  mov     [rbp+57h+var_30], ebx
0x1800853bf  mov     [rbp+57h+var_2C], 0FFFFFFFFh
0x1800853c6  mov     [rbp+57h+var_28], edx
0x1800853c9  lea     rax, WPP_GLOBAL_Control
0x1800853d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800853d7  cmp     rcx, rax
0x1800853da  jz      short loc_18008540C
0x1800853dc  test    byte ptr [rcx+1Ch], 4
0x1800853e0  jz      short loc_18008540C
0x1800853e2  cmp     [rcx+19h], sil
0x1800853e6  jb      short loc_18008540C
0x1800853e8  lea     edx, [rbx-38h]
0x1800853eb  mov     [rsp+0B0h+var_90], ebx
0x1800853ef  lea     r9, aChannelconfige; "ChannelConfigException"
0x1800853f6  lea     r8, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids
0x1800853fd  mov     rcx, [rcx+10h]
0x180085401  call    WPP_SF_sD
0x180085406  xor     edx, edx
0x180085408  lea     r8d, [rbx-56h]
0x18008540c  xorps   xmm0, xmm0
0x18008540f  movdqu  [rbp+57h+var_70], xmm0
0x180085414  mov     dword ptr [rbp+57h+var_60], edi
0x180085417  mov     dword ptr [rbp+57h+var_60+4], r8d
0x18008541b  mov     [rbp+57h+var_58], ebx
0x18008541e  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x180085425  mov     [rbp+57h+var_50], edx
0x180085428  mov     qword ptr [rbp+57h+pExceptionObject+8], rdx
0x18008542c  lea     rdx, _TI2?AVChannelConfigException@@; pThrowInfo
0x180085433  lea     rcx, [rbp+57h+var_70]; pExceptionObject
0x180085437  call    _CxxThrowException_0
0x18008543d  mov     rcx, rbx; this
0x180085440  call    ?GetCurrentIsolation@ChannelConfigWriter@@AEBA?AW4_EVT_CHANNEL_ISOLATION_TYPE@@XZ; ChannelConfigWriter::GetCurrentIsolation(void)
0x180085445  mov     edi, eax
0x180085447  mov     rcx, rbx; this
0x18008544a  call    ?GetCurrentEnabledValue@ChannelConfigWriter@@AEBA_NXZ; ChannelConfigWriter::GetCurrentEnabledValue(void)
0x18008544f  mov     dl, al
0x180085451  mov     byte ptr [rbp+57h+SecurityDescriptorSize], al
0x180085454  mov     cl, [rbx+0E8h]
0x18008545a  test    cl, 3
0x18008545d  jz      loc_180085618
0x180085463  xor     edx, edx
0x180085465  test    r12b, r12b
0x180085468  jnz     loc_180085589
0x18008546e  test    r13b, r13b
0x180085471  jnz     loc_180085589
0x180085477  test    sil, cl
0x18008547a  jz      short loc_1800854AF
0x18008547c  mov     rax, [rbx+118h]
  ... truncated ...
```
