# ManifestProcessor::ProcessProviderNode(AbstractDomElement &)

- ea: `0x14001663c`
- end: `0x1400175f1`
- name: `?ProcessProviderNode@ManifestProcessor@@AEAAXAEAVAbstractDomElement@@@Z`
- size: `4021`
- prototype: `void __fastcall(ManifestProcessor *__hidden this, struct AbstractDomElement *)`
- caller_count: `1`
- callee_count: `41`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140001ce0`

## callees

- `0x140001738`
- `0x140003480`
- `0x140003700`
- `0x140004ab0`
- `0x140004ae0`
- `0x140005600`
- `0x140006cd0`
- `0x140006db0`
- `0x140008170`
- `0x140009b58`
- `0x14000a460`
- `0x14000a4d8`
- `0x14000a5a8`
- `0x14000a6a0`
- `0x14000adf0`
- `0x14000cc80`
- `0x14000d62c`
- `0x14000d6e8`
- `0x140015898`
- `0x14001663c`
- `0x1400175f8`
- `0x140017618`
- `0x140017fbc`
- `0x140018148`
- `0x140018ce4`
- `0x140018d68`
- `0x140021b00`
- `0x140022cec`
- `0x140029de0`
- `0x140029f98`
- `0x140029fc4`
- `0x14002a238`
- `0x14002a328`
- `0x14002a4fc`
- `0x14002b59c`
- `0x14002bbe8`
- `0x14002ecf4`
- `0x14002f6c8`
- `0x140031804`
- `0x140031810`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017571`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017571`

## string_xrefs

- `0x1400172d9`: `helpLink`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall ManifestProcessor::ProcessProviderNode(void **this, struct AbstractDomElement *a2)
{
  PublisherConfigWriter *v4; // r13
  unsigned int v5; // edx
  const char *v6; // r8
  __int64 v7; // rax
  const char *v8; // r8
  const char *v9; // r8
  const char *v10; // r8
  const wchar_t **v11; // r12
  __int64 v12; // rax
  const char *v13; // r8
  struct AbstractDomElement **v14; // rdi
  struct AbstractDomElement *v15; // rbx
  __int64 *v16; // rdi
  __int64 v17; // r15
  const wchar_t *v18; // rax
  const char *v19; // r8
  const char *v20; // r8
  _BYTE *v21; // rdx
  _BYTE *v22; // r8
  __int64 v23; // rax
  const char *v24; // r8
  _BYTE *v25; // rdx
  _BYTE *v26; // r8
  __int64 v27; // rax
  const char *v28; // r8
  const char *v29; // r8
  _BYTE *v30; // rdx
  _BYTE *v31; // r8
  __int64 v32; // rax
  const char *v33; // r8
  const char *v34; // r8
  __int64 v35; // rcx
  unsigned int WinevtRegPath; // eax
  unsigned int v37; // r15d
  const char *v38; // r8
  const char *v39; // r8
  void *v40; // rdi
  HKEY *v41; // rax
  unsigned int RegKey; // eax
  const struct std::nothrow_t *v43; // rdx
  unsigned int v44; // r15d
  HKEY v45; // rdi
  PublisherConfigWriter *v46; // rax
  char v47; // r15
  const char *v48; // r8
  const char *v49; // r8
  const char *v50; // r8
  __int64 v51; // rax
  const char *v52; // r8
  ManifestProcessor *v53; // rcx
  PVOID v54; // rcx
  void *v55; // r14
  _BYTE *i; // rbx
  __int64 v57; // rdx
  const char *v58; // r8
  void *v59; // rsi
  __int64 v60; // r8
  __int64 v61; // rcx
  __int64 v62; // rbx
  __int64 v63; // r8
  const char *v64; // r8
  HKEY v65; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v66; // [rsp+48h] [rbp-B8h] BYREF
  __int16 *pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v68; // [rsp+58h] [rbp-A8h]
  __int64 v69; // [rsp+60h] [rbp-A0h]
  unsigned int v70; // [rsp+68h] [rbp-98h]
  __int64 v71; // [rsp+6Ch] [rbp-94h]
  char v72; // [rsp+74h] [rbp-8Ch]
  __int64 v73; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  struct AbstractDomElement *v75; // [rsp+88h] [rbp-78h] BYREF
  __int64 v76; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v77[2]; // [rsp+98h] [rbp-68h] BYREF
  char v78[8]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v79[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v80[4]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v81[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE *v82; // [rsp+100h] [rbp+0h]
  unsigned int v83[8]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v84[4]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *v85[4]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v86[32]; // [rsp+170h] [rbp+70h] BYREF
  struct _GUID v87; // [rsp+190h] [rbp+90h] BYREF

  v4 = 0;
  v75 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v83);
  v87 = 0;
  (*(void (__fastcall **)(struct AbstractDomElement *, __int64 *, const wchar_t *))(*(_QWORD *)a2 + 40LL))(
    a2,
    &v66,
    L"guid");
  if ( !v66 )
  {
    eventlog::ai::WarningMessage((eventlog::ai *)0x4F, v5);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, v6, 1021);
    throw (EvtException *)&pExceptionObject;
  }
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v83, v7) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v8, 1026);
    throw (EvtException *)&pExceptionObject;
  }
  if ( !tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(&v87, v83) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, v9, 1031);
    throw (EvtException *)&pExceptionObject;
  }
  wmi::AutoRef<AbstractDomAttribute>::Release(&v66);
  (*(void (__fastcall **)(struct AbstractDomElement *, __int64 *, const wchar_t *))(*(_QWORD *)a2 + 40LL))(
    a2,
    &v66,
    L"name");
  if ( !v66 )
  {
    eventlog::ai::WarningMessage((eventlog::ai *)0x47, v83[0]);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, v10, 1040);
    throw (EvtException *)&pExceptionObject;
  }
  v11 = (const wchar_t **)(this + 6);
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           this + 6,
                           v12) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v13, 1045);
    throw (EvtException *)&pExceptionObject;
  }
  wmi::AutoRef<AbstractDomAttribute>::Release(&v66);
  v14 = (struct AbstractDomElement **)(*(__int64 (__fastcall **)(struct AbstractDomElement *, HKEY *, const wchar_t *))(*(_QWORD *)a2 + 32LL))(
                                        a2,
                                        &v65,
                                        L"channels");
  wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v75);
  v75 = *v14;
  v15 = v75;
  *v14 = 0;
  wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v65);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>(v81);
  if ( v15 )
  {
    (*(void (__fastcall **)(struct AbstractDomElement *, HKEY *))(*(_QWORD *)v15 + 24LL))(v15, &v65);
    v66 = 0;
    while ( 1 )
    {
      v16 = (__int64 *)(*(__int64 (__fastcall **)(HKEY, char *))(*(_QWORD *)v65 + 8LL))(v65, v78);
      wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v66);
      v66 = *v16;
      v17 = v66;
      *v16 = 0;
      wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(v78);
      if ( !v17 )
        break;
      v18 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( !wcscmp_0(L"channel", v18) )
      {
        (*(void (__fastcall **)(__int64, __int64 *, const wchar_t *))(*(_QWORD *)v17 + 40LL))(v17, &v76, L"name");
        if ( !v76 )
        {
          eventlog::ai::WarningMessage((eventlog::ai *)0x49, v83[0], *v11);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
          }
          EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, v20, 1068);
          throw (EvtException *)&pExceptionObject;
        }
        v73 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::emplace<wchar_t const *,0>(
          v81,
          v77,
          &v73);
        if ( !v77[0] )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
          }
          EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v19, 1074);
          throw (EvtException *)&pExceptionObject;
        }
        wmi::AutoRef<AbstractDomAttribute>::Release(&v76);
      }
    }
    wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v66);
    wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v65);
  }
  ManifestProcessor::ValidatePublisherAndChannelOwner((ManifestProcessor *)this, &v87, (const struct StringSet *)v81);
  ManifestProcessor::RetractProviderNode((ManifestProcessor *)this, a2, (const struct StringSet *)v81);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v80);
  v21 = this[14];
  v22 = this[15];
  if ( v21 == v22 )
  {
    (*(void (__fastcall **)(struct AbstractDomElement *, HKEY *, const wchar_t *))(*(_QWORD *)a2 + 40LL))(
      a2,
      &v65,
      L"messageFileName");
    if ( v65 )
    {
      v23 = (*(__int64 (__fastcall **)(HKEY))(*(_QWORD *)v65 + 16LL))(v65);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               v80,
                               v23) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v24, 1103);
        throw (EvtException *)&pExceptionObject;
      }
    }
    wmi::AutoRef<AbstractDomAttribute>::Release(&v65);
  }
  else if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                v80,
                                v21,
                                (v22 - v21) >> 1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v29, 1111);
    throw (EvtException *)&pExceptionObject;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v79);
  v25 = this[10];
  v26 = this[11];
  if ( v25 == v26 )
  {
    (*(void (__fastcall **)(struct AbstractDomElement *, HKEY *, const wchar_t *))(*(_QWORD *)a2 + 40LL))(
      a2,
      &v65,
      L"resourceFileName");
    if ( v65 )
    {
      v27 = (*(__int64 (__fastcall **)(HKEY))(*(_QWORD *)v65 + 16LL))(v65);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               v79,
                               v27) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v28, 1123);
        throw (EvtException *)&pExceptionObject;
      }
    }
    wmi::AutoRef<AbstractDomAttribute>::Release(&v65);
  }
  else if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                v79,
                                v25,
                                (v26 - v25) >> 1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v34, 1131);
    throw (EvtException *)&pExceptionObject;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v84);
  v30 = this[18];
  v31 = this[19];
  if ( v30 == v31 )
  {
    (*(void (__fastcall **)(struct AbstractDomElement *, HKEY *, const wchar_t *))(*(_QWORD *)a2 + 40LL))(
      a2,
      &v65,
      L"parameterFileName");
    if ( v65 )
    {
      v32 = (*(__int64 (__fastcall **)(HKEY))(*(_QWORD *)v65 + 16LL))(v65);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               v84,
                               v32) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v33, 1143);
        throw (EvtException *)&pExceptionObject;
      }
    }
    wmi::AutoRef<AbstractDomAttribute>::Release(&v65);
  }
  else if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                v84,
                                v30,
                                (v31 - v30) >> 1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v38, 1151);
    throw (EvtException *)&pExceptionObject;
  }
  if ( !*((_BYTE *)this + 1) )
    ManifestProcessor::ValidateResourceFile(this, &v87, v79);
  v65 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v85);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v86);
  WinevtRegPath = RegistryPaths::GetWinevtRegPath(v35, &v65, v85, v86);
  v37 = WinevtRegPath;
  if ( WinevtRegPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, WinevtRegPath);
    }
    pExceptionObject = word_14003838A;
    v68 = 0;
    v69 = 0;
    v70 = v37;
    v71 = -1;
    v72 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           v85,
                           L"\\Publishers",
                           11) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v39, 1166);
    throw (EvtException *)&pExceptionObject;
  }
  hKey = 0;
  v40 = this[1];
  v41 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  RegKey = CreateRegKey(v65, v85[0], 0x2001Fu, 0, v41, 0, v40);
  v44 = RegKey;
  if ( RegKey )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, RegKey);
    }
    pExceptionObject = word_14003838A;
    v68 = 0;
    v69 = 0;
    v70 = v44;
    v71 = -1;
    v72 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v45 = hKey;
  v46 = (PublisherConfigWriter *)operator new(0x150u, v43);
  v73 = (__int64)v46;
  if ( v46 )
    v4 = PublisherConfigWriter::PublisherConfigWriter(v46, &v87, 0x20006u, 0, v45, this[1]);
  v73 = (__int64)v4;
  PublisherConfigWriteData::SetName((PublisherConfigWriter *)((char *)v4 + 144), *v11);
  v47 = 1;
  if ( v79[0] != v79[1] )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             (char *)v4 + 144,
                             v79[0]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ff2da5a7c3d7353b6f9322ae42c4201e_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v48, 43);
      throw (EvtException *)&pExceptionObject;
    }
    *((_BYTE *)v4 + 330) = 1;
  }
  if ( v80[0] != v80[1] )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             (char *)v4 + 176,
                             v80[0]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ff2da5a7c3d7353b6f9322ae42c4201e_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v49, 53);
      throw (EvtException *)&pExceptionObject;
    }
    *((_BYTE *)v4 + 331) = 1;
  }
  if ( v84[0] != v84[1] )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             (char *)v4 + 208,
                             v84[0]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ff2da5a7c3d7353b6f9322ae42c4201e_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v50, 63);
      throw (EvtException *)&pExceptionObject;
    }
    *((_BYTE *)v4 + 332) = 1;
  }
  (*(void (__fastcall **)(struct AbstractDomElement *, HKEY *, const wchar_t *))(*(_QWORD *)a2 + 40LL))(
    a2,
    &v65,
    L"helpLink");
  if ( v65 )
  {
    v51 = (*(__int64 (__fastcall **)(HKEY))(*(_QWORD *)v65 + 16LL))(v65);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             (char *)v4 + 240,
                             v51) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ff2da5a7c3d7353b6f9322ae42c4201e_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v52, 73);
      throw (EvtException *)&pExceptionObject;
    }
    *((_BYTE *)v4 + 333) = 1;
  }
  wmi::AutoRef<AbstractDomAttribute>::Release(&v65);
  if ( v15 )
  {
    ManifestProcessor::ProcessChannelsNode((ManifestProcessor *)this, &v87);
    ManifestProcessor::AddChannelReferences(v53, (PublisherConfigWriter *)((char *)v4 + 144), v15);
  }
  PublisherConfigWriter::Save(v4);
  v54 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&v87);
  }
  if ( v15 )
    ManifestProcessor::UpdateEtwSessions((ManifestProcessor *)this, &v87);
  if ( *(_BYTE *)this )
  {
    if ( v15 )
    {
      v55 = this[3];
      for ( i = v82;
            i != v81;
            i = (_BYTE *)utl::_TreeNodeHeader<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::_Traverse(
                           i,
                           v57) )
      {
        if ( !*(_QWORD *)utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_InsertImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &>(
                           v55,
                           v77,
                           v55,
                           i + 24) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
          }
          EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v58, 1227);
          throw (EvtException *)&pExceptionObject;
        }
        LOBYTE(v57) = 1;
      }
    }
    v59 = this[2];
    utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNode<utl::_TreeNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
      v54,
      &v66);
    v61 = v66;
    if ( v66 )
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        v66 + 24,
        v83);
    else
      v47 = 0;
    LOBYTE(v60) = v47;
    v62 = utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNodeCommit<utl::_TreeNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
            v61,
            &v66,
            v60);
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&v66);
    utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_EmplaceImpl(
      v59,
      v77,
      v63,
      v62);
    if ( !v77[0] )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v64, 1234);
      throw (EvtException *)&pExceptionObject;
    }
  }
  utl::unique_ptr<PublisherConfigWriter,utl::default_delete<PublisherConfigWriter>>::~unique_ptr<PublisherConfigWriter,utl::default_delete<PublisherConfigWriter>>(&v73);
  if ( hKey )
    RegCloseKey(hKey);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v86);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v85);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v84);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v79);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v80);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::clear(v81);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v83);
  wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v75);
}

```

## disassembly

```asm
0x14001663c  mov     [rsp-8+arg_10], rbx
0x140016641  push    rbp
0x140016642  push    rsi
0x140016643  push    rdi
0x140016644  push    r12
0x140016646  push    r13
0x140016648  push    r14
0x14001664a  push    r15
0x14001664c  lea     rbp, [rsp-0B0h]
0x140016654  sub     rsp, 1B0h
0x14001665b  mov     rax, cs:__security_cookie
0x140016662  xor     rax, rsp
0x140016665  mov     [rbp+0E0h+var_40], rax
0x14001666c  mov     r14, rdx
0x14001666f  mov     rsi, rcx
0x140016672  xor     r13d, r13d
0x140016675  mov     [rbp+0E0h+var_158], r13
0x140016679  lea     rcx, [rbp+0E0h+var_D0]
0x14001667d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140016682  nop
0x140016683  xorps   xmm0, xmm0
0x140016686  movups  xmmword ptr [rbp+0E0h+var_50.Data1], xmm0
0x14001668d  mov     rax, [r14]
0x140016690  lea     r8, aGuid_0; "guid"
0x140016697  lea     rdx, [rsp+1E0h+var_198]
0x14001669c  mov     rcx, r14
0x14001669f  mov     rax, [rax+28h]
0x1400166a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400166a8  nop
0x1400166a9  mov     rcx, [rsp+1E0h+var_198]
0x1400166ae  test    rcx, rcx
0x1400166b1  jnz     short loc_140016719
0x1400166b3  lea     ecx, [r13+4Fh]; this
0x1400166b7  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x1400166bc  lea     rdi, WPP_GLOBAL_Control
0x1400166c3  lea     esi, [r13+0Dh]
0x1400166c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400166ce  cmp     rcx, rdi
0x1400166d1  jz      short loc_1400166F5
0x1400166d3  test    byte ptr [rcx+1Ch], 4
0x1400166d7  jz      short loc_1400166F5
0x1400166d9  cmp     byte ptr [rcx+19h], 2
0x1400166dd  jb      short loc_1400166F5
0x1400166df  lea     edx, [rsi+2Ah]
0x1400166e2  mov     r9d, esi
0x1400166e5  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x1400166ec  mov     rcx, [rcx+10h]
0x1400166f0  call    WPP_SF_d
0x1400166f5  mov     r9d, 3FDh; int
0x1400166fb  mov     edx, esi; unsigned int
0x1400166fd  lea     rcx, [rsp+1E0h+pExceptionObject]; this
0x140016702  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140016707  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001670e  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x140016713  call    _CxxThrowException_0
0x140016719  mov     rax, [rcx]
0x14001671c  mov     rax, [rax+10h]
0x140016720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016725  mov     rdx, rax
0x140016728  lea     rcx, [rbp+0E0h+var_D0]
0x14001672c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x140016731  test    al, al
0x140016733  jnz     short loc_140016793
0x140016735  lea     rdi, WPP_GLOBAL_Control
0x14001673c  mov     ebx, 0Eh
0x140016741  mov     rcx, cs:WPP_GLOBAL_Control
0x140016748  cmp     rcx, rdi
0x14001674b  jz      short loc_14001676F
0x14001674d  test    byte ptr [rcx+1Ch], 4
0x140016751  jz      short loc_14001676F
0x140016753  cmp     byte ptr [rcx+19h], 2
0x140016757  jb      short loc_14001676F
0x140016759  lea     edx, [rbx+2Ah]
0x14001675c  mov     r9d, ebx
0x14001675f  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140016766  mov     rcx, [rcx+10h]
0x14001676a  call    WPP_SF_d
0x14001676f  mov     r9d, 402h; int
0x140016775  mov     edx, ebx; unsigned int
0x140016777  lea     rcx, [rsp+1E0h+pExceptionObject]; this
0x14001677c  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140016781  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140016788  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x14001678d  call    _CxxThrowException_0
0x140016793  lea     rdx, [rbp+0E0h+var_D0]
0x140016797  lea     rcx, [rbp+0E0h+var_50]
0x14001679e  call    ??$string_to_guid@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(_GUID *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x1400167a3  test    rax, rax
0x1400167a6  jnz     short loc_140016804
0x1400167a8  lea     rdi, WPP_GLOBAL_Control
0x1400167af  lea     esi, [rax+0Dh]
0x1400167b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400167b9  cmp     rcx, rdi
0x1400167bc  jz      short loc_1400167E0
0x1400167be  test    byte ptr [rcx+1Ch], 4
0x1400167c2  jz      short loc_1400167E0
0x1400167c4  cmp     byte ptr [rcx+19h], 2
0x1400167c8  jb      short loc_1400167E0
0x1400167ca  lea     edx, [rax+39h]
0x1400167cd  mov     r9d, esi
0x1400167d0  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x1400167d7  mov     rcx, [rcx+10h]
0x1400167db  call    WPP_SF_d
0x1400167e0  mov     r9d, 407h; int
0x1400167e6  mov     edx, esi; unsigned int
0x1400167e8  lea     rcx, [rsp+1E0h+pExceptionObject]; this
0x1400167ed  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400167f2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400167f9  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x1400167fe  call    _CxxThrowException_0
0x140016804  lea     rcx, [rsp+1E0h+var_198]
0x140016809  call    ?Release@?$AutoRef@VAbstractDomAttribute@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractDomAttribute>::Release(void)
0x14001680e  mov     rax, [r14]
0x140016811  lea     r8, aName_0; "name"
0x140016818  lea     rdx, [rsp+1E0h+var_198]
0x14001681d  mov     rcx, r14
0x140016820  mov     rax, [rax+28h]
0x140016824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016829  nop
0x14001682a  mov     rcx, [rsp+1E0h+var_198]
0x14001682f  test    rcx, rcx
0x140016832  jnz     short loc_1400168A0
0x140016834  mov     rdx, qword ptr [rbp+0E0h+var_D0]; unsigned int
0x140016838  mov     ecx, 47h ; 'G'; this
0x14001683d  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x140016842  lea     rdi, WPP_GLOBAL_Control
0x140016849  mov     esi, 0Dh
0x14001684e  mov     rcx, cs:WPP_GLOBAL_Control
0x140016855  cmp     rcx, rdi
0x140016858  jz      short loc_14001687C
0x14001685a  test    byte ptr [rcx+1Ch], 4
0x14001685e  jz      short loc_14001687C
0x140016860  cmp     byte ptr [rcx+19h], 2
0x140016864  jb      short loc_14001687C
0x140016866  lea     edx, [rsi+2Dh]
0x140016869  mov     r9d, esi
0x14001686c  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140016873  mov     rcx, [rcx+10h]
0x140016877  call    WPP_SF_d
0x14001687c  mov     r9d, 410h; int
0x140016882  mov     edx, esi; unsigned int
0x140016884  lea     rcx, [rsp+1E0h+pExceptionObject]; this
0x140016889  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14001688e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140016895  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x14001689a  call    _CxxThrowException_0
0x1400168a0  lea     r12, [rsi+30h]
0x1400168a4  mov     rax, [rcx]
0x1400168a7  mov     rax, [rax+10h]
0x1400168ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400168b0  mov     rdx, rax
0x1400168b3  mov     rcx, r12
0x1400168b6  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1400168bb  test    al, al
0x1400168bd  jnz     short loc_14001691D
0x1400168bf  lea     rdi, WPP_GLOBAL_Control
0x1400168c6  mov     ebx, 0Eh
0x1400168cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400168d2  cmp     rcx, rdi
0x1400168d5  jz      short loc_1400168F9
0x1400168d7  test    byte ptr [rcx+1Ch], 4
0x1400168db  jz      short loc_1400168F9
0x1400168dd  cmp     byte ptr [rcx+19h], 2
0x1400168e1  jb      short loc_1400168F9
0x1400168e3  lea     edx, [rbx+2Dh]
0x1400168e6  mov     r9d, ebx
0x1400168e9  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x1400168f0  mov     rcx, [rcx+10h]
0x1400168f4  call    WPP_SF_d
0x1400168f9  mov     r9d, 415h; int
0x1400168ff  mov     edx, ebx; unsigned int
0x140016901  lea     rcx, [rsp+1E0h+pExceptionObject]; this
0x140016906  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14001690b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140016912  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x140016917  call    _CxxThrowException_0
0x14001691d  lea     rcx, [rsp+1E0h+var_198]
0x140016922  call    ?Release@?$AutoRef@VAbstractDomAttribute@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractDomAttribute>::Release(void)
0x140016927  mov     rax, [r14]
0x14001692a  lea     r8, aChannels_2; "channels"
0x140016931  lea     rdx, [rsp+1E0h+var_1A0]
0x140016936  mov     rcx, r14
0x140016939  mov     rax, [rax+20h]
0x14001693d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016942  mov     rdi, rax
0x140016945  lea     rcx, [rbp+0E0h+var_158]
0x140016949  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x14001694e  mov     rbx, [rdi]
0x140016951  mov     [rbp+0E0h+var_158], rbx
0x140016955  mov     [rdi], r13
0x140016958  lea     rcx, [rsp+1E0h+var_1A0]
0x14001695d  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x140016962  lea     rcx, [rbp+0E0h+var_F0]
0x140016966  call    ??0?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>(void)
0x14001696b  nop
0x14001696c  test    rbx, rbx
0x14001696f  jz      loc_140016B39
0x140016975  mov     rax, [rbx]
0x140016978  lea     rdx, [rsp+1E0h+var_1A0]
0x14001697d  mov     rcx, rbx
0x140016980  mov     rax, [rax+18h]
0x140016984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016989  nop
0x14001698a  mov     [rsp+1E0h+var_198], r13
0x14001698f  mov     rcx, [rsp+1E0h+var_1A0]
0x140016994  mov     rax, [rcx]
0x140016997  lea     rdx, [rbp+0E0h+var_138]
0x14001699b  mov     rax, [rax+8]
0x14001699f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400169a4  mov     rdi, rax
0x1400169a7  lea     rcx, [rsp+1E0h+var_198]
0x1400169ac  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x1400169b1  mov     r15, [rdi]
0x1400169b4  mov     [rsp+1E0h+var_198], r15
0x1400169b9  mov     [rdi], r13
0x1400169bc  test    r15, r15
0x1400169bf  setnz   dil
0x1400169c3  lea     rcx, [rbp+0E0h+var_138]
0x1400169c7  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x1400169cc  test    dil, dil
0x1400169cf  jz      loc_140016B24
0x1400169d5  mov     rax, [r15]
0x1400169d8  mov     rcx, r15
0x1400169db  mov     rax, [rax+10h]
0x1400169df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400169e4  mov     rdx, rax; String2
0x1400169e7  lea     rcx, aChannel; "channel"
0x1400169ee  call    wcscmp_0
0x1400169f3  test    eax, eax
0x1400169f5  jnz     short loc_14001698F
0x1400169f7  mov     rax, [r15]
0x1400169fa  lea     r8, aName_0; "name"
0x140016a01  lea     rdx, [rbp+0E0h+var_150]
0x140016a05  mov     rcx, r15
0x140016a08  mov     rax, [rax+28h]
0x140016a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016a11  nop
0x140016a12  mov     rcx, [rbp+0E0h+var_150]
0x140016a16  test    rcx, rcx
0x140016a19  jz      loc_140016AB4
0x140016a1f  mov     rax, [rcx]
0x140016a22  mov     rax, [rax+10h]
0x140016a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016a2b  mov     [rsp+1E0h+var_168], rax
0x140016a30  lea     r8, [rsp+1E0h+var_168]
0x140016a35  lea     rdx, [rbp+0E0h+var_148]
0x140016a39  lea     rcx, [rbp+0E0h+var_F0]
0x140016a3d  call    ??$emplace@PEB_W$0A@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeConstIt@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@_N@1@$$QEAPEB_W@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::emplace<wchar_t const *,0>(wchar_t const * &&)
0x140016a42  cmp     [rbp+0E0h+var_148], r13
0x140016a46  jz      short loc_140016A56
0x140016a48  lea     rcx, [rbp+0E0h+var_150]
0x140016a4c  call    ?Release@?$AutoRef@VAbstractDomAttribute@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractDomAttribute>::Release(void)
0x140016a51  jmp     loc_14001698F
0x140016a56  lea     rdi, WPP_GLOBAL_Control
0x140016a5d  mov     ebx, 0Eh
0x140016a62  mov     rcx, cs:WPP_GLOBAL_Control
0x140016a69  cmp     rcx, rdi
0x140016a6c  jz      short loc_140016A90
0x140016a6e  test    byte ptr [rcx+1Ch], 4
0x140016a72  jz      short loc_140016A90
0x140016a74  cmp     byte ptr [rcx+19h], 2
0x140016a78  jb      short loc_140016A90
0x140016a7a  lea     edx, [rbx+2Fh]
0x140016a7d  mov     r9d, ebx
0x140016a80  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140016a87  mov     rcx, [rcx+10h]
0x140016a8b  call    WPP_SF_d
0x140016a90  mov     r9d, 432h; int
0x140016a96  mov     edx, ebx; unsigned int
0x140016a98  lea     rcx, [rsp+1E0h+pExceptionObject]; this
0x140016a9d  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140016aa2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140016aa9  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x140016aae  call    _CxxThrowException_0
0x140016ab4  mov     r8, [r12]
0x140016ab8  mov     rdx, qword ptr [rbp+0E0h+var_D0]; unsigned int
0x140016abc  mov     ecx, 49h ; 'I'; this
0x140016ac1  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x140016ac6  lea     rdi, WPP_GLOBAL_Control
0x140016acd  mov     esi, 0Dh
0x140016ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x140016ad9  cmp     rcx, rdi
0x140016adc  jz      short loc_140016B00
0x140016ade  test    byte ptr [rcx+1Ch], 4
0x140016ae2  jz      short loc_140016B00
0x140016ae4  cmp     byte ptr [rcx+19h], 2
0x140016ae8  jb      short loc_140016B00
0x140016aea  lea     edx, [rsi+2Fh]
0x140016aed  mov     r9d, esi
0x140016af0  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140016af7  mov     rcx, [rcx+10h]
0x140016afb  call    WPP_SF_d
0x140016b00  mov     r9d, 42Ch; int
0x140016b06  mov     edx, esi; unsigned int
0x140016b08  lea     rcx, [rsp+1E0h+pExceptionObject]; this
0x140016b0d  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140016b12  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140016b19  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x140016b1e  call    _CxxThrowException_0
0x140016b24  lea     rcx, [rsp+1E0h+var_198]
  ... truncated ...
```
