# ChannelConfigWriter::Validate(bool)

- ea: `0x1400203a8`
- end: `0x1400215a0`
- name: `?Validate@ChannelConfigWriter@@QEAAX_N@Z`
- size: `4600`
- prototype: `void __fastcall(ChannelConfigWriter *__hidden this, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400178bc`

## callees

- `0x140008870`
- `0x140015878`
- `0x140019348`
- `0x1400201e8`
- `0x1400203a8`
- `0x1400215a8`
- `0x14002bc70`
- `0x14002bca0`
- `0x14002bcc8`
- `0x14002c6e4`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400208d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400208d2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400208c4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400208c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ChannelConfigWriter::Validate(ChannelConfigWriter *this, char a2)
{
  char v3; // al
  char v4; // r15
  char v5; // cl
  char v6; // r14
  int v7; // edi
  int v8; // edi
  char v9; // al
  ULONG v10; // esi
  int v11; // edi
  char v12; // al
  int v13; // edi
  int v14; // edi
  int v15; // edi
  int v16; // edi
  bool v17; // si
  PSECURITY_DESCRIPTOR *v18; // rax
  DWORD LastError; // eax
  int v20; // edi
  char v21; // al
  int v22; // edi
  int v23; // edi
  int v24; // edi
  int v25; // edi
  int v26; // edi
  int v27; // edi
  int v28; // edi
  int v29; // edi
  int v30; // edi
  int v31; // edi
  int v32; // edi
  int v33; // edi
  int v34; // edi
  int v35; // edi
  int v36; // edi
  int v37; // edi
  int v38; // edi
  int v39; // edi
  int v40; // edi
  int v41; // edi
  _QWORD v42[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v43; // [rsp+40h] [rbp-29h] BYREF
  __int64 v44; // [rsp+48h] [rbp-21h]
  int v45; // [rsp+50h] [rbp-19h]
  int v46; // [rsp+54h] [rbp-15h]
  int v47; // [rsp+58h] [rbp-11h]
  int v48; // [rsp+5Ch] [rbp-Dh]
  int v49; // [rsp+60h] [rbp-9h]
  __int64 pExceptionObject; // [rsp+68h] [rbp-1h] BYREF
  __int64 v51; // [rsp+70h] [rbp+7h]
  int v52; // [rsp+78h] [rbp+Fh]
  int v53; // [rsp+7Ch] [rbp+13h]
  int v54; // [rsp+80h] [rbp+17h]
  int v55; // [rsp+84h] [rbp+1Bh]
  int v56; // [rsp+88h] [rbp+1Fh]
  __int64 v57; // [rsp+D0h] [rbp+67h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+D8h] [rbp+6Fh] BYREF

  LOBYTE(SecurityDescriptorSize) = a2;
  v42[0] = *((_QWORD *)this + 35);
  v42[1] = (__int64)(*((_QWORD *)this + 36) - v42[0]) >> 1;
  v3 = IsCoreChannel(v42);
  v4 = v3;
  v5 = *((_BYTE *)this + 352);
  if ( v5 != 1 || (v6 = 1, v3) )
    v6 = 0;
  if ( (*((_BYTE *)this + 236) & 3) != 0 )
  {
    ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 4u);
    v7 = v47;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24);
    }
    pExceptionObject = v43;
    v51 = v44;
    v52 = v45;
    v53 = v46;
    v54 = v7;
    v55 = v48;
    v56 = v49;
    v44 = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 235) & 3) != 0 )
  {
    ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 3u);
    v8 = v47;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25);
    }
    pExceptionObject = v43;
    v51 = v44;
    v52 = v45;
    v53 = v46;
    v54 = v8;
    v55 = v48;
    v56 = v49;
    v44 = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  v9 = *((_BYTE *)this + 234);
  if ( (v9 & 1) != 0 )
  {
    v10 = *((_DWORD *)this + 12);
    if ( v10 >= 4 )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 2u);
      v11 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 26);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v11;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
  }
  else
  {
    if ( (v9 & 2) != 0 )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 2u);
      v41 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v41;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
    if ( v5 == 1 )
    {
      v10 = 0;
    }
    else
    {
      SecurityDescriptorSize = 0;
      v10 = 1;
      if ( !RegReadDWORDValueNoThrow(*((HKEY *)this + 32), (const wchar_t *)1, L"Type", &SecurityDescriptorSize) )
        v10 = SecurityDescriptorSize;
    }
  }
  v12 = *((_BYTE *)this + 233);
  if ( (v12 & 1) != 0 )
  {
    if ( v6 || v4 )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 1u);
      v14 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 29);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v14;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
    if ( *((_DWORD *)this + 13) > 2u )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 1u);
      v13 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 30);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v13;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
  }
  else
  {
    if ( (v12 & 2) != 0 && (v6 || v4) )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 1u);
      v15 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v15;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
    ChannelConfigWriter::GetCurrentIsolation(this);
  }
  ChannelConfigWriter::GetCurrentEnabledValue(this);
  if ( (*((_BYTE *)this + 232) & 3) != 0 && (v6 || v4) )
  {
    ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0);
    v16 = v47;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 32);
    }
    pExceptionObject = v43;
    v51 = v44;
    v52 = v45;
    v53 = v46;
    v54 = v16;
    v55 = v48;
    v56 = v49;
    v44 = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  v17 = v10 - 2 <= 1;
  if ( (*((_BYTE *)this + 237) & 3) != 0 && *((_QWORD *)this + 2) != *((_QWORD *)this + 3) )
  {
    v57 = 0;
    SecurityDescriptorSize = 0;
    v18 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v57);
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(*((LPCWSTR *)this + 2), 1u, v18, &SecurityDescriptorSize) )
    {
      LastError = GetLastError();
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, LastError, 5u);
      v20 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 36);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v20;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
    tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v57);
  }
  v21 = *((_BYTE *)this + 238);
  if ( (v21 & 3) != 0 )
  {
    if ( v4 || v6 )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 6u);
      v23 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 37);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v23;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
    if ( (!*((_BYTE *)this + 224) || (v21 & 2) != 0) && *((_BYTE *)this + 225) )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 6u);
      v22 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 38);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v22;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
  }
  if ( (*((_BYTE *)this + 239) & 3) != 0 )
  {
    if ( v4 || v6 || v17 )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 7u);
      v25 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 40);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v25;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
    if ( !*((_BYTE *)this + 224) && *((_BYTE *)this + 225) )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 7u);
      v24 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 41);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v24;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
  }
  if ( (*((_BYTE *)this + 240) & 3) != 0 && (v4 || v6) )
  {
    ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 8u);
    v26 = v47;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 42);
    }
    pExceptionObject = v43;
    v51 = v44;
    v52 = v45;
    v53 = v46;
    v54 = v26;
    v55 = v48;
    v56 = v49;
    v44 = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 241) & 3) != 0 && (v4 || v6) )
  {
    ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 9u);
    v27 = v47;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 44);
    }
    pExceptionObject = v43;
    v51 = v44;
    v52 = v45;
    v53 = v46;
    v54 = v27;
    v55 = v48;
    v56 = v49;
    v44 = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 252) & 1) != 0 )
  {
    if ( v4 || v6 || !v17 )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0x14u);
      v29 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 46);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v29;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
    if ( *((_DWORD *)this + 26) > 0x10u )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0x14u);
      v28 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 48);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v28;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
  }
  if ( (*((_BYTE *)this + 242) & 3) != 0 && (v4 || v6 || !v17) )
  {
    ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0xAu);
    v30 = v47;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 49);
    }
    pExceptionObject = v43;
    v51 = v44;
    v52 = v45;
    v53 = v46;
    v54 = v30;
    v55 = v48;
    v56 = v49;
    v44 = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 243) & 3) != 0 && (v4 || v6 || !v17) )
  {
    ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0xBu);
    v31 = v47;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 51);
    }
    pExceptionObject = v43;
    v51 = v44;
    v52 = v45;
    v53 = v46;
    v54 = v31;
    v55 = v48;
    v56 = v49;
    v44 = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 244) & 3) != 0 && *((_DWORD *)this + 12) != 3 )
  {
    ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0xCu);
    v32 = v47;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 53);
    }
    pExceptionObject = v43;
    v51 = v44;
    v52 = v45;
    v53 = v46;
    v54 = v32;
    v55 = v48;
    v56 = v49;
    v44 = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 245) & 3) != 0 && !v17 )
  {
    ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0xDu);
    v33 = v47;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 55);
    }
    pExceptionObject = v43;
    v51 = v44;
    v52 = v45;
    v53 = v46;
    v54 = v33;
    v55 = v48;
    v56 = v49;
    v44 = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 246) & 3) != 0 && !v17 )
  {
    ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0xEu);
    v34 = v47;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 57);
    }
    pExceptionObject = v43;
    v51 = v44;
    v52 = v45;
    v53 = v46;
    v54 = v34;
    v55 = v48;
    v56 = v49;
    v44 = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 247) & 3) != 0 && !v17 )
  {
    ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0xFu);
    v35 = v47;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 59);
    }
    pExceptionObject = v43;
    v51 = v44;
    v52 = v45;
    v53 = v46;
    v54 = v35;
    v55 = v48;
    v56 = v49;
    v44 = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 248) & 3) != 0 && !v17 )
  {
    ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0x10u);
    v36 = v47;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 61);
    }
    pExceptionObject = v43;
    v51 = v44;
    v52 = v45;
    v53 = v46;
    v54 = v36;
    v55 = v48;
    v56 = v49;
    v44 = 0;
    throw (ChannelConfigException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 249) & 3) != 0 )
  {
    if ( !v17 )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0x11u);
      v37 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 63);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v37;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
    if ( *((_BYTE *)this + 112) >= 2u )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0x11u);
      v38 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 64);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v38;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
  }
  if ( (*((_BYTE *)this + 250) & 3) != 0 )
  {
    if ( !v17 )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0x12u);
      v39 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 66);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v39;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
    if ( *((_BYTE *)this + 113) >= 2u )
    {
      ChannelConfigException::ChannelConfigException((ChannelConfigException *)&v43, 0x12u);
      v40 = v47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 67);
      }
      pExceptionObject = v43;
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v54 = v40;
      v55 = v48;
      v56 = v49;
      v44 = 0;
      throw (ChannelConfigException *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x1400203a8  mov     [rsp-8+arg_10], rbx
0x1400203ad  mov     byte ptr [rsp-8+SecurityDescriptorSize], dl
0x1400203b1  push    rbp
0x1400203b2  push    rsi
0x1400203b3  push    rdi
0x1400203b4  push    r12
0x1400203b6  push    r13
0x1400203b8  push    r14
0x1400203ba  push    r15
0x1400203bc  lea     rbp, [rsp-27h]
0x1400203c1  sub     rsp, 90h
0x1400203c8  mov     rdi, rcx
0x1400203cb  mov     rax, [rcx+118h]
0x1400203d2  mov     [rbp+57h+var_90], rax
0x1400203d6  mov     rdx, [rcx+120h]
0x1400203dd  sub     rdx, rax
0x1400203e0  sar     rdx, 1
0x1400203e3  mov     [rbp+57h+var_88], rdx
0x1400203e7  lea     rcx, [rbp+57h+var_90]
0x1400203eb  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1400203f0  mov     r15b, al
0x1400203f3  mov     cl, [rdi+160h]
0x1400203f9  xor     r12d, r12d
0x1400203fc  lea     edx, [r12+1]; wchar_t *
0x140020401  cmp     cl, dl
0x140020403  jnz     short loc_14002040C
0x140020405  test    al, al
0x140020407  mov     r14b, dl
0x14002040a  jz      short loc_14002040F
0x14002040c  mov     r14b, r12b
0x14002040f  mov     r13d, 3
0x140020415  test    [rdi+0ECh], r13b
0x14002041c  jz      loc_1400204A6
0x140020422  lea     edx, [r13+1]; unsigned int
0x140020426  lea     rcx, [rbp+57h+var_80]; this
0x14002042a  call    ??0ChannelConfigException@@QEAA@K@Z; ChannelConfigException::ChannelConfigException(ulong)
0x14002042f  nop
0x140020430  lea     rax, WPP_GLOBAL_Control
0x140020437  mov     rdi, [rbp+57h+var_68]
0x14002043b  mov     rcx, cs:WPP_GLOBAL_Control
0x140020442  cmp     rcx, rax
0x140020445  jz      short loc_140020466
0x140020447  test    byte ptr [rcx+1Ch], 4
0x14002044b  jz      short loc_140020466
0x14002044d  lea     ebx, [r13-1]
0x140020451  cmp     [rcx+19h], bl
0x140020454  jb      short loc_140020466
0x140020456  lea     edx, [rbx+16h]
0x140020459  mov     [rsp+0C0h+var_A0], edi
0x14002045d  mov     rcx, [rcx+10h]
0x140020461  call    WPP_SF_sD
0x140020466  mov     rax, [rbp+57h+var_80]
0x14002046a  mov     [rbp+57h+pExceptionObject], rax
0x14002046e  mov     rax, [rbp+57h+var_78]
0x140020472  mov     [rbp+57h+var_50], rax
0x140020476  mov     eax, [rbp+57h+var_70]
0x140020479  mov     [rbp+57h+var_48], eax
0x14002047c  mov     eax, [rbp+57h+var_6C]
0x14002047f  mov     [rbp+57h+var_44], eax
0x140020482  mov     [rbp+57h+var_40], edi
0x140020485  mov     eax, dword ptr [rbp+57h+var_68+4]
0x140020488  mov     [rbp+57h+var_3C], eax
0x14002048b  mov     eax, [rbp+57h+var_60]
0x14002048e  mov     [rbp+57h+var_38], eax
0x140020491  mov     [rbp+57h+var_78], r12
0x140020495  lea     rdx, _TI2?AVChannelConfigException@@; pThrowInfo
0x14002049c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400204a0  call    _CxxThrowException_0
0x1400204a6  test    [rdi+0EBh], r13b
0x1400204ad  jz      loc_140020537
0x1400204b3  mov     edx, r13d; unsigned int
0x1400204b6  lea     rcx, [rbp+57h+var_80]; this
0x1400204ba  call    ??0ChannelConfigException@@QEAA@K@Z; ChannelConfigException::ChannelConfigException(ulong)
0x1400204bf  nop
0x1400204c0  lea     rax, WPP_GLOBAL_Control
0x1400204c7  mov     rdi, [rbp+57h+var_68]
0x1400204cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400204d2  cmp     rcx, rax
0x1400204d5  jz      short loc_1400204F7
0x1400204d7  test    byte ptr [rcx+1Ch], 4
0x1400204db  jz      short loc_1400204F7
0x1400204dd  mov     ebx, 2
0x1400204e2  cmp     [rcx+19h], bl
0x1400204e5  jb      short loc_1400204F7
0x1400204e7  lea     edx, [rbx+17h]
0x1400204ea  mov     [rsp+0C0h+var_A0], edi
0x1400204ee  mov     rcx, [rcx+10h]
0x1400204f2  call    WPP_SF_sD
0x1400204f7  mov     rax, [rbp+57h+var_80]
0x1400204fb  mov     [rbp+57h+pExceptionObject], rax
0x1400204ff  mov     rax, [rbp+57h+var_78]
0x140020503  mov     [rbp+57h+var_50], rax
0x140020507  mov     eax, [rbp+57h+var_70]
0x14002050a  mov     [rbp+57h+var_48], eax
0x14002050d  mov     eax, [rbp+57h+var_6C]
0x140020510  mov     [rbp+57h+var_44], eax
0x140020513  mov     [rbp+57h+var_40], edi
0x140020516  mov     eax, dword ptr [rbp+57h+var_68+4]
0x140020519  mov     [rbp+57h+var_3C], eax
0x14002051c  mov     eax, [rbp+57h+var_60]
0x14002051f  mov     [rbp+57h+var_38], eax
0x140020522  mov     [rbp+57h+var_78], r12
0x140020526  lea     rdx, _TI2?AVChannelConfigException@@; pThrowInfo
0x14002052d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140020531  call    _CxxThrowException_0
0x140020537  mov     al, [rdi+0EAh]
0x14002053d  mov     ebx, 2
0x140020542  test    dl, al
0x140020544  jz      loc_1400205DC
0x14002054a  mov     esi, [rdi+30h]
0x14002054d  cmp     esi, ebx
0x14002054f  jbe     loc_140020615
0x140020555  cmp     esi, r13d
0x140020558  jz      loc_140020615
0x14002055e  mov     edx, ebx; unsigned int
0x140020560  lea     rcx, [rbp+57h+var_80]; this
0x140020564  call    ??0ChannelConfigException@@QEAA@K@Z; ChannelConfigException::ChannelConfigException(ulong)
0x140020569  nop
0x14002056a  lea     rax, WPP_GLOBAL_Control
0x140020571  mov     rdi, [rbp+57h+var_68]
0x140020575  mov     rcx, cs:WPP_GLOBAL_Control
0x14002057c  cmp     rcx, rax
0x14002057f  jz      short loc_14002059C
0x140020581  test    byte ptr [rcx+1Ch], 4
0x140020585  jz      short loc_14002059C
0x140020587  cmp     [rcx+19h], bl
0x14002058a  jb      short loc_14002059C
0x14002058c  lea     edx, [rbx+18h]
0x14002058f  mov     [rsp+0C0h+var_A0], edi
0x140020593  mov     rcx, [rcx+10h]
0x140020597  call    WPP_SF_sD
0x14002059c  mov     rax, [rbp+57h+var_80]
0x1400205a0  mov     [rbp+57h+pExceptionObject], rax
0x1400205a4  mov     rax, [rbp+57h+var_78]
0x1400205a8  mov     [rbp+57h+var_50], rax
0x1400205ac  mov     eax, [rbp+57h+var_70]
0x1400205af  mov     [rbp+57h+var_48], eax
0x1400205b2  mov     eax, [rbp+57h+var_6C]
0x1400205b5  mov     [rbp+57h+var_44], eax
0x1400205b8  mov     [rbp+57h+var_40], edi
0x1400205bb  mov     eax, dword ptr [rbp+57h+var_68+4]
0x1400205be  mov     [rbp+57h+var_3C], eax
0x1400205c1  mov     eax, [rbp+57h+var_60]
0x1400205c4  mov     [rbp+57h+var_38], eax
0x1400205c7  mov     [rbp+57h+var_78], r12
0x1400205cb  lea     rdx, _TI2?AVChannelConfigException@@; pThrowInfo
0x1400205d2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400205d6  call    _CxxThrowException_0
0x1400205dc  test    bl, al
0x1400205de  jnz     loc_140021505
0x1400205e4  cmp     cl, dl
0x1400205e6  jnz     short loc_1400205ED
0x1400205e8  mov     esi, r12d
0x1400205eb  jmp     short loc_140020615
0x1400205ed  mov     [rbp+57h+SecurityDescriptorSize], r12d
0x1400205f1  lea     r9, [rbp+57h+SecurityDescriptorSize]; unsigned int *
0x1400205f5  lea     r8, aType_0; "Type"
0x1400205fc  mov     rcx, [rdi+100h]; HKEY
0x140020603  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x140020608  mov     edx, 1; unsigned int
0x14002060d  mov     esi, edx
0x14002060f  test    eax, eax
0x140020611  cmovz   esi, [rbp+57h+SecurityDescriptorSize]
0x140020615  mov     al, [rdi+0E9h]
0x14002061b  test    dl, al
0x14002061d  jz      loc_140020743
0x140020623  test    r14b, r14b
0x140020626  jnz     loc_1400206C5
0x14002062c  test    r15b, r15b
0x14002062f  jnz     loc_1400206C5
0x140020635  cmp     [rdi+34h], edx
0x140020638  jbe     loc_1400207DB
0x14002063e  cmp     [rdi+34h], ebx
0x140020641  jz      loc_1400207DB
0x140020647  lea     rcx, [rbp+57h+var_80]; this
0x14002064b  call    ??0ChannelConfigException@@QEAA@K@Z; ChannelConfigException::ChannelConfigException(ulong)
0x140020650  nop
0x140020651  lea     rax, WPP_GLOBAL_Control
0x140020658  mov     rdi, [rbp+57h+var_68]
0x14002065c  mov     rcx, cs:WPP_GLOBAL_Control
0x140020663  cmp     rcx, rax
0x140020666  jz      short loc_140020685
0x140020668  test    byte ptr [rcx+1Ch], 4
0x14002066c  jz      short loc_140020685
0x14002066e  cmp     [rcx+19h], bl
0x140020671  jb      short loc_140020685
0x140020673  mov     edx, 1Eh
0x140020678  mov     [rsp+0C0h+var_A0], edi
0x14002067c  mov     rcx, [rcx+10h]
0x140020680  call    WPP_SF_sD
0x140020685  mov     rax, [rbp+57h+var_80]
0x140020689  mov     [rbp+57h+pExceptionObject], rax
0x14002068d  mov     rax, [rbp+57h+var_78]
0x140020691  mov     [rbp+57h+var_50], rax
0x140020695  mov     eax, [rbp+57h+var_70]
0x140020698  mov     [rbp+57h+var_48], eax
0x14002069b  mov     eax, [rbp+57h+var_6C]
0x14002069e  mov     [rbp+57h+var_44], eax
0x1400206a1  mov     [rbp+57h+var_40], edi
0x1400206a4  mov     eax, dword ptr [rbp+57h+var_68+4]
0x1400206a7  mov     [rbp+57h+var_3C], eax
0x1400206aa  mov     eax, [rbp+57h+var_60]
0x1400206ad  mov     [rbp+57h+var_38], eax
0x1400206b0  mov     [rbp+57h+var_78], r12
0x1400206b4  lea     rdx, _TI2?AVChannelConfigException@@; pThrowInfo
0x1400206bb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400206bf  call    _CxxThrowException_0
0x1400206c5  lea     rcx, [rbp+57h+var_80]; this
0x1400206c9  call    ??0ChannelConfigException@@QEAA@K@Z; ChannelConfigException::ChannelConfigException(ulong)
0x1400206ce  nop
0x1400206cf  lea     rax, WPP_GLOBAL_Control
0x1400206d6  mov     rdi, [rbp+57h+var_68]
0x1400206da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400206e1  cmp     rcx, rax
0x1400206e4  jz      short loc_140020703
0x1400206e6  test    byte ptr [rcx+1Ch], 4
0x1400206ea  jz      short loc_140020703
0x1400206ec  cmp     [rcx+19h], bl
0x1400206ef  jb      short loc_140020703
0x1400206f1  mov     edx, 1Dh
0x1400206f6  mov     [rsp+0C0h+var_A0], edi
0x1400206fa  mov     rcx, [rcx+10h]
0x1400206fe  call    WPP_SF_sD
0x140020703  mov     rax, [rbp+57h+var_80]
0x140020707  mov     [rbp+57h+pExceptionObject], rax
0x14002070b  mov     rax, [rbp+57h+var_78]
0x14002070f  mov     [rbp+57h+var_50], rax
0x140020713  mov     eax, [rbp+57h+var_70]
0x140020716  mov     [rbp+57h+var_48], eax
0x140020719  mov     eax, [rbp+57h+var_6C]
0x14002071c  mov     [rbp+57h+var_44], eax
0x14002071f  mov     [rbp+57h+var_40], edi
0x140020722  mov     eax, dword ptr [rbp+57h+var_68+4]
0x140020725  mov     [rbp+57h+var_3C], eax
0x140020728  mov     eax, [rbp+57h+var_60]
0x14002072b  mov     [rbp+57h+var_38], eax
0x14002072e  mov     [rbp+57h+var_78], r12
0x140020732  lea     rdx, _TI2?AVChannelConfigException@@; pThrowInfo
0x140020739  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14002073d  call    _CxxThrowException_0
0x140020743  test    bl, al
0x140020745  jz      loc_1400207D3
0x14002074b  test    r14b, r14b
0x14002074e  jnz     short loc_140020755
0x140020750  test    r15b, r15b
0x140020753  jz      short loc_1400207D3
0x140020755  lea     rcx, [rbp+57h+var_80]; this
0x140020759  call    ??0ChannelConfigException@@QEAA@K@Z; ChannelConfigException::ChannelConfigException(ulong)
0x14002075e  nop
0x14002075f  lea     rax, WPP_GLOBAL_Control
0x140020766  mov     rdi, [rbp+57h+var_68]
0x14002076a  mov     rcx, cs:WPP_GLOBAL_Control
0x140020771  cmp     rcx, rax
0x140020774  jz      short loc_140020793
0x140020776  test    byte ptr [rcx+1Ch], 4
0x14002077a  jz      short loc_140020793
0x14002077c  cmp     [rcx+19h], bl
0x14002077f  jb      short loc_140020793
0x140020781  mov     edx, 1Fh
0x140020786  mov     [rsp+0C0h+var_A0], edi
0x14002078a  mov     rcx, [rcx+10h]
0x14002078e  call    WPP_SF_sD
0x140020793  mov     rax, [rbp+57h+var_80]
0x140020797  mov     [rbp+57h+pExceptionObject], rax
0x14002079b  mov     rax, [rbp+57h+var_78]
0x14002079f  mov     [rbp+57h+var_50], rax
0x1400207a3  mov     eax, [rbp+57h+var_70]
0x1400207a6  mov     [rbp+57h+var_48], eax
0x1400207a9  mov     eax, [rbp+57h+var_6C]
0x1400207ac  mov     [rbp+57h+var_44], eax
0x1400207af  mov     [rbp+57h+var_40], edi
0x1400207b2  mov     eax, dword ptr [rbp+57h+var_68+4]
0x1400207b5  mov     [rbp+57h+var_3C], eax
0x1400207b8  mov     eax, [rbp+57h+var_60]
0x1400207bb  mov     [rbp+57h+var_38], eax
0x1400207be  mov     [rbp+57h+var_78], r12
0x1400207c2  lea     rdx, _TI2?AVChannelConfigException@@; pThrowInfo
0x1400207c9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400207cd  call    _CxxThrowException_0
0x1400207d3  mov     rcx, rdi; this
0x1400207d6  call    ?GetCurrentIsolation@ChannelConfigWriter@@AEBA?AW4_EVT_CHANNEL_ISOLATION_TYPE@@XZ; ChannelConfigWriter::GetCurrentIsolation(void)
0x1400207db  mov     rcx, rdi; this
0x1400207de  call    ?GetCurrentEnabledValue@ChannelConfigWriter@@AEBA_NXZ; ChannelConfigWriter::GetCurrentEnabledValue(void)
0x1400207e3  test    [rdi+0E8h], r13b
0x1400207ea  jz      loc_14002087E
0x1400207f0  test    r14b, r14b
0x1400207f3  jnz     short loc_1400207FE
0x1400207f5  test    r15b, r15b
0x1400207f8  jz      loc_14002087E
0x1400207fe  xor     edx, edx; unsigned int
0x140020800  lea     rcx, [rbp+57h+var_80]; this
0x140020804  call    ??0ChannelConfigException@@QEAA@K@Z; ChannelConfigException::ChannelConfigException(ulong)
0x140020809  nop
0x14002080a  lea     rax, WPP_GLOBAL_Control
0x140020811  mov     rdi, [rbp+57h+var_68]
0x140020815  mov     rcx, cs:WPP_GLOBAL_Control
0x14002081c  cmp     rcx, rax
0x14002081f  jz      short loc_14002083E
0x140020821  test    byte ptr [rcx+1Ch], 4
0x140020825  jz      short loc_14002083E
  ... truncated ...
```
