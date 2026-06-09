# Channel::ResetPublishing(ChannelConfigSnapshot &&,ulong)

- ea: `0x18000349c`
- end: `0x180003d95`
- name: `?ResetPublishing@Channel@@AEAAX$$QEAVChannelConfigSnapshot@@K@Z`
- size: `2297`
- prototype: `__int64 __fastcall(WCHAR *this, const struct ChannelConfigSnapshot *, char)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180002ae4`

## callees

- `0x18000349c`
- `0x180003d9c`
- `0x180003de0`
- `0x180003e4c`
- `0x180006fb0`
- `0x180014bd0`
- `0x180016250`
- `0x180017b60`
- `0x18002ede4`
- `0x18003e14c`
- `0x180047fd8`
- `0x1800587c8`
- `0x18005c600`
- `0x1800626e8`
- `0x18006ea40`
- `0x180074eb8`
- `0x18008aaf8`
- `0x180092008`
- `0x18009aee0`
- `0x1800a3a60`
- `0x1800aca34`
- `0x1800acb8c`
- `0x1800ace24`
- `0x1800acfec`
- `0x1800ad238`
- `0x1800bf0bc`
- `0x1800d334c`
- `0x1800d3364`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a43`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000357d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003798`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003863`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000357d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003798`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003863`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180003a35`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180003a35`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180003bd4`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180003bd4`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Channel::ResetPublishing(WCHAR *this, const struct ChannelConfigSnapshot *a2, char a3)
{
  const struct ChannelConfigSnapshot *v3; // r13
  WCHAR *v4; // r14
  LPWSTR v5; // rbx
  char v6; // di
  EventSession **v7; // r15
  struct _GUID *v8; // rbx
  struct _ACL *v9; // rdi
  int v10; // r8d
  bool v11; // al
  struct _GUID v12; // xmm6
  PSRWLOCK v13; // rbx
  _DWORD *Ptr; // r8
  _QWORD *v15; // rdx
  WCHAR *v16; // rax
  EventSession *v17; // rax
  __int64 v18; // rbx
  EventSession *v19; // rcx
  unsigned int v20; // ebx
  void *ChannelAccess; // rax
  DWORD LastError; // ebx
  unsigned int v23; // ebx
  DWORD v24; // ebx
  struct _GUID *v25; // rbx
  bool *v26; // rdi
  int v27; // ecx
  __int64 result; // rax
  __int64 v29; // [rsp+0h] [rbp-2B8h] BYREF
  char v30; // [rsp+40h] [rbp-278h]
  WINBOOL bDaclPresent; // [rsp+44h] [rbp-274h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+48h] [rbp-270h] BYREF
  struct _GUID *v33; // [rsp+50h] [rbp-268h] BYREF
  PSRWLOCK v34; // [rsp+58h] [rbp-260h] BYREF
  WINBOOL bDaclDefaulted[2]; // [rsp+60h] [rbp-258h] BYREF
  PACL pDacl; // [rsp+68h] [rbp-250h] BYREF
  struct _GUID Buf1; // [rsp+70h] [rbp-248h] BYREF
  WCHAR *v38; // [rsp+80h] [rbp-238h]
  bool *v39; // [rsp+88h] [rbp-230h]
  WCHAR *v40; // [rsp+90h] [rbp-228h]
  LPWSTR pObjectName[4]; // [rsp+A0h] [rbp-218h] BYREF
  const struct ChannelConfigSnapshot *v42; // [rsp+C0h] [rbp-1F8h]
  _QWORD v43[3]; // [rsp+C8h] [rbp-1F0h] BYREF
  unsigned int v44; // [rsp+E0h] [rbp-1D8h]
  int v45; // [rsp+E4h] [rbp-1D4h]
  int v46; // [rsp+E8h] [rbp-1D0h]
  char v47; // [rsp+ECh] [rbp-1CCh]
  _QWORD v48[3]; // [rsp+F0h] [rbp-1C8h] BYREF
  unsigned int v49; // [rsp+108h] [rbp-1B0h]
  int v50; // [rsp+10Ch] [rbp-1ACh]
  int v51; // [rsp+110h] [rbp-1A8h]
  char v52; // [rsp+114h] [rbp-1A4h]
  _QWORD v53[3]; // [rsp+118h] [rbp-1A0h] BYREF
  DWORD v54; // [rsp+130h] [rbp-188h]
  int v55; // [rsp+134h] [rbp-184h]
  int v56; // [rsp+138h] [rbp-180h]
  char v57; // [rsp+13Ch] [rbp-17Ch]
  __int128 pExceptionObject; // [rsp+140h] [rbp-178h] BYREF
  __int64 v59; // [rsp+150h] [rbp-168h]
  int v60; // [rsp+158h] [rbp-160h]
  int v61; // [rsp+15Ch] [rbp-15Ch]
  int v62; // [rsp+160h] [rbp-158h]
  __int128 v63; // [rsp+168h] [rbp-150h] BYREF
  __int64 v64; // [rsp+178h] [rbp-140h]
  DWORD v65; // [rsp+180h] [rbp-138h]
  int v66; // [rsp+184h] [rbp-134h]
  int v67; // [rsp+188h] [rbp-130h]
  EvtException *v68; // [rsp+190h] [rbp-128h] BYREF
  EvtException *v69; // [rsp+198h] [rbp-120h] BYREF
  __int64 v70; // [rsp+1A0h] [rbp-118h] BYREF
  LPCWCH v71[11]; // [rsp+1A8h] [rbp-110h] BYREF
  char v72[8]; // [rsp+200h] [rbp-B8h] BYREF
  LPCWCH lpString1[11]; // [rsp+208h] [rbp-B0h] BYREF

  v3 = a2;
  v4 = this;
  v38 = this;
  v5 = this;
  pObjectName[0] = this;
  v42 = a2;
  v34 = g_service + 45;
  v39 = (bool *)(this + 42);
  if ( *((_BYTE *)this + 84) || (v6 = 1, (a3 & 4) != 0) )
    v6 = 0;
  v30 = v6;
  v7 = (EventSession **)(this + 48);
  v40 = this + 48;
  pSecurityDescriptor = this + 48;
  if ( *((_QWORD *)this + 12) && v6 )
  {
    SessionConfig::SessionConfig((SessionConfig *)v72, a2);
    if ( !*((_BYTE *)v3 + 251) || CompareStringOrdinal(lpString1[0], -1, *((LPCWCH *)*v7 + 2), -1, 1) != 2 )
    {
      if ( *((_BYTE *)v4 + 86) )
      {
        if ( *((_BYTE *)v4 + 87) )
        {
          *(_OWORD *)pObjectName = *((_OWORD *)v4 + 11);
          EventSession::Enable(*v7, (LPCGUID)pObjectName, 0, 0, 0, 0, 1);
        }
        else if ( !*((_BYTE *)v4 + 85) )
        {
          bDaclPresent = 0;
          v33 = 0;
          EventService::GetPublisherListForChannel(
            g_service,
            *((const WCHAR **)v4 + 17),
            &bDaclPresent,
            0,
            (__int64)&v33);
          v8 = v33;
          v9 = (struct _ACL *)&v33[bDaclPresent];
          pDacl = v9;
          while ( 1 )
          {
            *(_QWORD *)bDaclDefaulted = v8;
            if ( v8 == (struct _GUID *)v9 )
              break;
            try
            {
              Buf1 = *v8;
              EventSession::UpdateProviderFromAutologgerSettings((HKEY *)*v7, &Buf1);
            }
            catch ( EvtException *v68 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_D_guid_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  (_DWORD)WPP_GLOBAL_Control,
                  v10,
                  *((_DWORD *)v68 + 6),
                  *(__int64 *)bDaclDefaulted,
                  *(_QWORD *)(*((_QWORD *)v38 + 12) + 16LL));
              }
              v8 = *(struct _GUID **)bDaclDefaulted;
              v9 = pDacl;
              v4 = v38;
              v3 = v42;
              v7 = (EventSession **)v40;
            }
            ++v8;
          }
          utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v33);
          v5 = pObjectName[0];
          v6 = v30;
        }
      }
      else
      {
        EventSession::RetractSession(*v7);
      }
      wmi::AutoRef<PublisherMetadata>::Release(v7);
      *v7 = 0;
    }
    utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(lpString1);
  }
  utl::_OptionalData2<ChannelConfigSnapshot>::_AssignVal<ChannelConfigSnapshot>(v4 + 84, v3);
  if ( !*((_BYTE *)v5 + 424) )
    __int2c();
  v11 = (unsigned __int8)(*((_BYTE *)v5 + 417) - 2) <= 1u;
  *((_BYTE *)v4 + 876) = v11;
  if ( v11 )
    *((_BYTE *)v4 + 877) = *((_BYTE *)v5 + 328) == 0;
  v12 = (struct _GUID)*((_OWORD *)v5 + 11);
  Buf1 = v12;
  *((_BYTE *)v4 + 87) = memcmp_0(&Buf1, &GUID_NULL, 0x10u) != 0;
  if ( !*((_BYTE *)v5 + 419) || BYTE4(g_service[60].Ptr) )
  {
    result = wmi::AutoRef<PublisherMetadata>::Release(v7);
    *v7 = 0;
    return result;
  }
  SessionConfig::SessionConfig((SessionConfig *)&v70, (const struct ChannelConfigSnapshot *)(v4 + 84));
  v13 = v34;
  if ( *((_BYTE *)v4 + 85) )
    goto LABEL_40;
  Ptr = v34[4].Ptr;
  if ( Ptr[20] || *((_DWORD *)v34[5].Ptr + 20) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids, 5023);
    }
    pExceptionObject = 0;
    v59 = 0;
    v60 = 5023;
    v61 = -1;
    v62 = 579;
    throw (EvtException *)&pExceptionObject;
  }
  if ( CompareStringOrdinal(v71[0], -1, *(LPCWCH *)(*((_QWORD *)Ptr + 12) + 16LL), -1, 1) != 2 )
  {
    if ( !*((_BYTE *)v4 + 85)
      && CompareStringOrdinal(v71[0], -1, *(LPCWCH *)(*((_QWORD *)v13[5].Ptr + 12) + 16LL), -1, 1) == 2 )
    {
      v15 = v13[5].Ptr;
      goto LABEL_39;
    }
LABEL_40:
    if ( !*((_QWORD *)v4 + 12) )
    {
      v16 = (WCHAR *)operator new(0x68u);
      pObjectName[0] = v16;
      if ( v16 )
        v17 = EventSession::EventSession((EventSession *)v16, v71[0], *((_BYTE *)v4 + 84));
      else
        v17 = 0;
      wmi::AutoRef<EventSession>::operator=(pSecurityDescriptor, v17);
    }
    v18 = *((_QWORD *)v4 + 12);
    SessionConfig::BuildTracePropsFromChannelRegistryConfig((SessionConfig *)&v70, v18 + 48);
    *(_DWORD *)(v18 + 96) = *(unsigned __int8 *)(v70 + 49);
    *((_BYTE *)v4 + 86) = 0;
    v19 = *v7;
    if ( v6 )
    {
      EventSession::CreateOrUpdateSession(v19);
    }
    else
    {
      v20 = EventSession::TryOpenExistingSession(v19);
      if ( v20 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids, v20);
        }
        v43[0] = &word_1800EC961;
        v43[1] = 0;
        v43[2] = 0;
        v44 = v20;
        v45 = -1;
        v46 = -1;
        v47 = 0;
        throw (EvtException *)v43;
      }
    }
    if ( *((_BYTE *)v4 + 876) )
    {
      ChannelAccess = Channel::GetChannelAccess((Channel *)v4, v39);
      pSecurityDescriptor = 0;
      bDaclPresent = 0;
      bDaclDefaulted[0] = 0;
      pDacl = 0;
      if ( ChannelAccess )
      {
        TransformSDPermissions(
          ChannelAccess,
          &stru_18010F5E8,
          (__int64)&unk_1800EF3F0,
          *(void **)(*((_QWORD *)v4 + 8) + 80LL),
          0,
          &pSecurityDescriptor);
        if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, bDaclDefaulted) )
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 1287;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids,
              LastError);
          }
          v63 = 0;
          v64 = 0;
          v65 = LastError;
          v66 = -1;
          v67 = 688;
          throw (EvtException *)&v63;
        }
      }
      EventSession::GetLogName(*v7, &Buf1);
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(pObjectName);
      v23 = ExpandEnvStringNoThrow(*(LPCWSTR *)&Buf1.Data1);
      if ( v23 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids, v23);
        }
        v48[0] = &word_1800EC961;
        v48[1] = 0;
        v48[2] = 0;
        v49 = v23;
        v50 = -1;
        v51 = -1;
        v52 = 0;
        throw (EvtException *)v48;
      }
      v24 = SetNamedSecurityInfoW(
              pObjectName[0],
              SE_FILE_OBJECT,
              4u,
              0,
              0,
              (PACL)((unsigned __int64)pDacl & -(__int64)(bDaclPresent != 0)),
              0);
      if ( v24 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids, v24);
        }
        v53[0] = &word_1800EC961;
        v53[1] = 0;
        v53[2] = 0;
        v54 = v24;
        v55 = -1;
        v56 = -1;
        v57 = 0;
        throw (EvtException *)v53;
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pObjectName);
      tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&pSecurityDescriptor);
    }
    else if ( (a3 & 8) == 0 )
    {
      EventSession::StartProcessingEvents(*v7);
    }
    goto LABEL_78;
  }
  v15 = v13[4].Ptr;
LABEL_39:
  wmi::AutoRef<EventSession>::operator=(pSecurityDescriptor, v15[12]);
  *((_BYTE *)v4 + 86) = 1;
LABEL_78:
  if ( v6 )
  {
    if ( *((_BYTE *)v4 + 87) )
    {
      Buf1 = v12;
      EventSession::UpdateProviderFromAutologgerSettings((HKEY *)*v7, &Buf1);
    }
    else if ( !*((_BYTE *)v4 + 85) )
    {
      LODWORD(v33) = 0;
      v34 = 0;
      EventService::GetPublisherListForChannel(g_service, *((const WCHAR **)v4 + 17), &v33, 0, (__int64)&v34);
      v25 = (struct _GUID *)v34;
      v26 = (bool *)&v34[2 * (unsigned int)v33];
      v39 = v26;
      while ( 1 )
      {
        pSecurityDescriptor = v25;
        if ( v25 == (struct _GUID *)v26 )
          break;
        try
        {
          Buf1 = *v25;
          EventSession::UpdateProviderFromAutologgerSettings((HKEY *)*v7, &Buf1);
        }
        catch ( EvtException *v69 )
        {
          if ( (Microsoft_Windows_EventlogEnableBits & 1) != 0 )
            McTemplateU0qzj_EventWriteTransfer(
              v27,
              (unsigned int)&v29,
              *((_DWORD *)v69 + 6),
              *((_QWORD *)v38 + 17),
              (__int64)pSecurityDescriptor);
          v25 = (struct _GUID *)pSecurityDescriptor;
          v26 = v39;
          v7 = (EventSession **)v40;
        }
        ++v25;
      }
      utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v34);
    }
  }
  return utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(v71);
}

```

## disassembly

```asm
0x18000349c  mov     rax, rsp
0x18000349f  mov     [rax+18h], r8d
0x1800034a3  push    rbx
0x1800034a4  push    rsi
0x1800034a5  push    rdi
0x1800034a6  push    r12
0x1800034a8  push    r13
0x1800034aa  push    r14
0x1800034ac  push    r15
0x1800034ae  sub     rsp, 280h
0x1800034b5  movaps  xmmword ptr [rax-48h], xmm6
0x1800034b9  mov     rax, cs:__security_cookie
0x1800034c0  xor     rax, rsp
0x1800034c3  mov     [rsp+2B8h+var_58], rax
0x1800034cb  mov     r13, rdx
0x1800034ce  mov     r14, rcx
0x1800034d1  mov     [rsp+2B8h+var_238], rcx
0x1800034d9  mov     rbx, rcx
0x1800034dc  mov     [rsp+2B8h+pObjectName], rcx
0x1800034e4  mov     [rsp+2B8h+var_1F8], rdx
0x1800034ec  mov     rax, cs:?g_service@@3PEAVEventService@@EA; EventService * g_service
0x1800034f3  add     rax, 168h
0x1800034f9  mov     [rsp+2B8h+var_260], rax
0x1800034fe  lea     rax, [rcx+54h]
0x180003502  mov     [rsp+2B8h+var_230], rax
0x18000350a  xor     esi, esi
0x18000350c  cmp     [rax], sil
0x18000350f  jnz     short loc_18000351A
0x180003511  test    r8b, 4
0x180003515  mov     dil, 1
0x180003518  jz      short loc_18000351D
0x18000351a  mov     dil, sil
0x18000351d  mov     [rsp+2B8h+var_278], dil
0x180003522  lea     r15, [rcx+60h]
0x180003526  mov     [rsp+2B8h+var_228], r15
0x18000352e  mov     [rsp+2B8h+pSecurityDescriptor], r15
0x180003533  cmp     [r15], rsi
0x180003536  jz      loc_1800036AF
0x18000353c  test    dil, dil
0x18000353f  jz      loc_1800036AF
0x180003545  lea     rcx, [rsp+2B8h+var_B8]; this
0x18000354d  call    ??0SessionConfig@@QEAA@AEBVChannelConfigSnapshot@@@Z; SessionConfig::SessionConfig(ChannelConfigSnapshot const &)
0x180003552  nop
0x180003553  or      r12d, 0FFFFFFFFh
0x180003557  cmp     [r13+0FBh], sil
0x18000355e  jz      short loc_18000358C
0x180003560  mov     r8, [r15]
0x180003563  mov     [rsp+2B8h+bIgnoreCase], 1; bIgnoreCase
0x18000356b  mov     r9d, r12d; cchCount2
0x18000356e  mov     r8, [r8+10h]; lpString2
0x180003572  mov     edx, r12d; cchCount1
0x180003575  mov     rcx, [rsp+2B8h+lpString1]; lpString1
0x18000357d  call    cs:__imp_CompareStringOrdinal
0x180003583  cmp     eax, 2
0x180003586  jz      loc_1800036A0
0x18000358c  cmp     [r14+56h], sil
0x180003590  jnz     short loc_18000359F
0x180003592  mov     rcx, [r15]; this
0x180003595  call    ?RetractSession@EventSession@@QEAAXXZ; EventSession::RetractSession(void)
0x18000359a  jmp     loc_180003695
0x18000359f  cmp     [r14+57h], sil
0x1800035a3  jz      short loc_1800035E0
0x1800035a5  movups  xmm0, xmmword ptr [r14+0B0h]
0x1800035ad  movdqu  xmmword ptr [rsp+2B8h+pObjectName], xmm0
0x1800035b6  mov     byte ptr [rsp+2B8h+pSacl], 1; bool
0x1800035bb  mov     [rsp+2B8h+var_290], rsi; unsigned __int64
0x1800035c0  mov     qword ptr [rsp+2B8h+bIgnoreCase], rsi; ULONGLONG
0x1800035c5  xor     r9d, r9d; unsigned int
0x1800035c8  xor     r8d, r8d; bool
0x1800035cb  lea     rdx, [rsp+2B8h+pObjectName]; ProviderId
0x1800035d3  mov     rcx, [r15]; this
0x1800035d6  call    ?Enable@EventSession@@QEAAXU_GUID@@_NK_K21@Z; EventSession::Enable(_GUID,bool,ulong,unsigned __int64,unsigned __int64,bool)
0x1800035db  jmp     loc_180003695
0x1800035e0  cmp     [r14+55h], sil
0x1800035e4  jnz     loc_180003695
0x1800035ea  mov     [rsp+2B8h+bDaclPresent], esi
0x1800035ee  mov     [rsp+2B8h+var_268], rsi
0x1800035f3  lea     rax, [rsp+2B8h+var_268]
0x1800035f8  mov     qword ptr [rsp+2B8h+bIgnoreCase], rax
0x1800035fd  xor     r9d, r9d
0x180003600  lea     r8, [rsp+2B8h+bDaclPresent]
0x180003605  mov     rdx, [r14+88h]
0x18000360c  mov     rcx, cs:?g_service@@3PEAVEventService@@EA; EventService * g_service
0x180003613  call    ?GetPublisherListForChannel@EventService@@QEAAXPEB_WAEAKPEAV?$unique_ptr@$$BY0A@PEA_WU?$default_delete@$$BY0A@PEA_W@utl@@@utl@@PEAV?$unique_ptr@$$BY0A@U_GUID@@U?$default_delete@$$BY0A@U_GUID@@@utl@@@3@@Z; EventService::GetPublisherListForChannel(wchar_t const *,ulong &,utl::unique_ptr<wchar_t * [0],utl::default_delete<wchar_t * [0]>> *,utl::unique_ptr<_GUID [0],utl::default_delete<_GUID [0]>> *)
0x180003618  mov     rbx, [rsp+2B8h+var_268]
0x18000361d  mov     edi, [rsp+2B8h+bDaclPresent]
0x180003621  shl     rdi, 4
0x180003625  add     rdi, rbx
0x180003628  mov     [rsp+2B8h+pDacl], rdi
0x18000362d  mov     qword ptr [rsp+2B8h+bDaclDefaulted], rbx
0x180003632  cmp     rbx, rdi
0x180003635  jz      short loc_18000367E
0x180003637  movups  xmm0, xmmword ptr [rbx]
0x18000363a  movdqu  [rsp+2B8h+Buf1], xmm0
0x180003640  lea     rdx, [rsp+2B8h+Buf1]; struct _GUID
0x180003645  mov     rcx, [r15]; this
0x180003648  call    ?UpdateProviderFromAutologgerSettings@EventSession@@QEAAXU_GUID@@@Z; EventSession::UpdateProviderFromAutologgerSettings(_GUID)
0x18000364d  nop
0x18000364e  jmp     short loc_180003678
0x180003650  xor     esi, esi
0x180003652  or      r12d, 0FFFFFFFFh
0x180003656  mov     rbx, qword ptr [rsp+2B8h+bDaclDefaulted]
0x18000365b  mov     rdi, [rsp+2B8h+pDacl]
0x180003660  mov     r14, [rsp+2B8h+var_238]
0x180003668  mov     r13, [rsp+2B8h+var_1F8]
0x180003670  mov     r15, [rsp+2B8h+var_228]
0x180003678  add     rbx, 10h
0x18000367c  jmp     short loc_18000362D
0x18000367e  lea     rcx, [rsp+2B8h+var_268]
0x180003683  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x180003688  mov     rbx, [rsp+2B8h+pObjectName]
0x180003690  mov     dil, [rsp+2B8h+var_278]
0x180003695  mov     rcx, r15
0x180003698  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18000369d  mov     [r15], rsi
0x1800036a0  lea     rcx, [rsp+2B8h+lpString1]
0x1800036a8  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@QEAA@XZ; utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(void)
0x1800036ad  jmp     short loc_1800036B3
0x1800036af  or      r12d, 0FFFFFFFFh
0x1800036b3  lea     rcx, [r14+0A8h]
0x1800036ba  mov     rdx, r13
0x1800036bd  call    ??$_AssignVal@VChannelConfigSnapshot@@@?$_OptionalData2@VChannelConfigSnapshot@@@utl@@QEAAX$$QEAVChannelConfigSnapshot@@@Z; utl::_OptionalData2<ChannelConfigSnapshot>::_AssignVal<ChannelConfigSnapshot>(ChannelConfigSnapshot &&)
0x1800036c2  cmp     [rbx+1A8h], sil
0x1800036c9  jnz     short loc_1800036CD
0x1800036cb  int     2Ch; Windows NT - assertion failure
0x1800036cd  mov     al, [rbx+1A1h]
0x1800036d3  sub     al, 2
0x1800036d5  cmp     al, 1
0x1800036d7  setbe   al
0x1800036da  mov     [r14+36Ch], al
0x1800036e1  test    al, al
0x1800036e3  jz      short loc_1800036F6
0x1800036e5  cmp     [rbx+148h], sil
0x1800036ec  setz    al
0x1800036ef  mov     [r14+36Dh], al
0x1800036f6  movups  xmm6, xmmword ptr [rbx+0B0h]
0x1800036fd  movaps  [rsp+2B8h+Buf1], xmm6
0x180003702  mov     r8d, 10h; Size
0x180003708  lea     rdx, GUID_NULL; Buf2
0x18000370f  lea     rcx, [rsp+2B8h+Buf1]; Buf1
0x180003714  call    memcmp_0
0x180003719  test    eax, eax
0x18000371b  setnz   al
0x18000371e  mov     [r14+57h], al
0x180003722  cmp     [rbx+1A3h], sil
0x180003729  jz      loc_180003D5F
0x18000372f  mov     rax, cs:?g_service@@3PEAVEventService@@EA; EventService * g_service
0x180003736  cmp     [rax+1E4h], sil
0x18000373d  jnz     loc_180003D5F
0x180003743  lea     rdx, [r14+0A8h]; struct ChannelConfigSnapshot *
0x18000374a  lea     rcx, [rsp+2B8h+var_118]; this
0x180003752  call    ??0SessionConfig@@QEAA@AEBVChannelConfigSnapshot@@@Z; SessionConfig::SessionConfig(ChannelConfigSnapshot const &)
0x180003757  nop
0x180003758  mov     rbx, [rsp+2B8h+var_260]
0x18000375d  cmp     [r14+55h], sil
0x180003761  jnz     loc_18000388A
0x180003767  mov     r8, [rbx+20h]
0x18000376b  cmp     [r8+50h], esi
0x18000376f  jnz     short loc_1800037B0
0x180003771  mov     rax, [rbx+28h]
0x180003775  cmp     [rax+50h], esi
0x180003778  jnz     short loc_1800037B0
0x18000377a  mov     r8, [r8+60h]
0x18000377e  mov     [rsp+2B8h+bIgnoreCase], 1; bIgnoreCase
0x180003786  mov     r9d, r12d; cchCount2
0x180003789  mov     r8, [r8+10h]; lpString2
0x18000378d  mov     edx, r12d; cchCount1
0x180003790  mov     rcx, [rsp+2B8h+var_110]; lpString1
0x180003798  call    cs:__imp_CompareStringOrdinal
0x18000379e  cmp     eax, 2
0x1800037a1  jnz     loc_18000383B
0x1800037a7  mov     rdx, [rbx+20h]
0x1800037ab  jmp     loc_180003872
0x1800037b0  lea     rax, WPP_GLOBAL_Control
0x1800037b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037be  cmp     rcx, rax
0x1800037c1  jz      short loc_1800037ED
0x1800037c3  test    dword ptr [rcx+1Ch], 800h
0x1800037ca  jz      short loc_1800037ED
0x1800037cc  cmp     byte ptr [rcx+19h], 2
0x1800037d0  jb      short loc_1800037ED
0x1800037d2  mov     edx, 15h
0x1800037d7  mov     r9d, 139Fh
0x1800037dd  lea     r8, WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids
0x1800037e4  mov     rcx, [rcx+10h]
0x1800037e8  call    WPP_SF_d
0x1800037ed  xorps   xmm0, xmm0
0x1800037f0  movdqu  [rsp+2B8h+pExceptionObject], xmm0
0x1800037f9  mov     [rsp+2B8h+var_168], 0
0x180003805  mov     [rsp+2B8h+var_160], 139Fh
0x180003810  mov     [rsp+2B8h+var_15C], 0FFFFFFFFh
0x18000381b  mov     [rsp+2B8h+var_158], 243h
0x180003826  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000382d  lea     rcx, [rsp+2B8h+pExceptionObject]; pExceptionObject
0x180003835  call    _CxxThrowException_0
0x18000383b  cmp     [r14+55h], sil
0x18000383f  jnz     short loc_18000388A
0x180003841  mov     rax, [rbx+28h]
0x180003845  mov     r8, [rax+60h]
0x180003849  mov     [rsp+2B8h+bIgnoreCase], 1; bIgnoreCase
0x180003851  mov     r9d, r12d; cchCount2
0x180003854  mov     r8, [r8+10h]; lpString2
0x180003858  mov     edx, r12d; cchCount1
0x18000385b  mov     rcx, [rsp+2B8h+var_110]; lpString1
0x180003863  call    cs:__imp_CompareStringOrdinal
0x180003869  cmp     eax, 2
0x18000386c  jnz     short loc_18000388A
0x18000386e  mov     rdx, [rbx+28h]
0x180003872  mov     rdx, [rdx+60h]
0x180003876  mov     rcx, [rsp+2B8h+pSecurityDescriptor]
0x18000387b  call    ??4?$AutoRef@VEventSession@@@wmi@@QEAAAEAV01@PEAVEventSession@@@Z; wmi::AutoRef<EventSession>::operator=(EventSession *)
0x180003880  mov     byte ptr [r14+56h], 1
0x180003885  jmp     loc_180003C90
0x18000388a  cmp     [r14+60h], rsi
0x18000388e  jnz     short loc_1800038CD
0x180003890  mov     ecx, 68h ; 'h'; dwBytes
0x180003895  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000389a  mov     [rsp+2B8h+pObjectName], rax
0x1800038a2  test    rax, rax
0x1800038a5  jz      short loc_1800038BD
0x1800038a7  mov     r8b, [r14+54h]; bool
0x1800038ab  mov     rdx, [rsp+2B8h+var_110]; wchar_t *
0x1800038b3  mov     rcx, rax; this
0x1800038b6  call    ??0EventSession@@QEAA@PEB_W_N@Z; EventSession::EventSession(wchar_t const *,bool)
0x1800038bb  jmp     short loc_1800038C0
0x1800038bd  mov     rax, rsi
0x1800038c0  mov     rdx, rax
0x1800038c3  mov     rcx, [rsp+2B8h+pSecurityDescriptor]
0x1800038c8  call    ??4?$AutoRef@VEventSession@@@wmi@@QEAAAEAV01@PEAVEventSession@@@Z; wmi::AutoRef<EventSession>::operator=(EventSession *)
0x1800038cd  mov     rbx, [r14+60h]
0x1800038d1  lea     rdx, [rbx+30h]
0x1800038d5  lea     rcx, [rsp+2B8h+var_118]; this
0x1800038dd  call    ?BuildTracePropsFromChannelRegistryConfig@SessionConfig@@QEBAPEAU_EVENT_TRACE_PROPERTIES@@AEAV?$vector@EV?$allocator@E@utl@@@utl@@@Z; SessionConfig::BuildTracePropsFromChannelRegistryConfig(utl::vector<uchar,utl::allocator<uchar>> &)
0x1800038e2  mov     rax, [rsp+2B8h+var_118]
0x1800038ea  movzx   ecx, byte ptr [rax+31h]
0x1800038ee  mov     [rbx+60h], ecx
0x1800038f1  mov     [r14+56h], sil
0x1800038f5  mov     rcx, [r15]; this
0x1800038f8  test    dil, dil
0x1800038fb  jz      short loc_18000392A
0x1800038fd  call    ?CreateOrUpdateSession@EventSession@@QEAAXXZ; EventSession::CreateOrUpdateSession(void)
0x180003902  cmp     [r14+36Ch], sil
0x180003909  jnz     loc_1800039C9
0x18000390f  test    [rsp+2B8h+arg_10], 8
0x180003917  jnz     loc_180003C90
0x18000391d  mov     rcx, [r15]; this
0x180003920  call    ?StartProcessingEvents@EventSession@@QEAAXXZ; EventSession::StartProcessingEvents(void)
0x180003925  jmp     loc_180003C90
0x18000392a  call    ?TryOpenExistingSession@EventSession@@QEAAKXZ; EventSession::TryOpenExistingSession(void)
0x18000392f  mov     ebx, eax
0x180003931  test    eax, eax
0x180003933  jz      short loc_180003902
0x180003935  lea     rax, WPP_GLOBAL_Control
0x18000393c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003943  cmp     rcx, rax
0x180003946  jz      short loc_18000396F
0x180003948  test    dword ptr [rcx+1Ch], 800h
0x18000394f  jz      short loc_18000396F
0x180003951  cmp     byte ptr [rcx+19h], 2
0x180003955  jb      short loc_18000396F
0x180003957  mov     edx, 16h
0x18000395c  mov     r9d, ebx
0x18000395f  lea     r8, WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids
0x180003966  mov     rcx, [rcx+10h]
0x18000396a  call    WPP_SF_d
0x18000396f  lea     rax, word_1800EC961
0x180003976  mov     [rsp+2B8h+var_1F0], rax
0x18000397e  mov     [rsp+2B8h+var_1E8], rsi
0x180003986  mov     [rsp+2B8h+var_1E0], 0
0x180003992  mov     [rsp+2B8h+var_1D8], ebx
0x180003999  mov     [rsp+2B8h+var_1D4], 0FFFFFFFFh
0x1800039a4  mov     [rsp+2B8h+var_1D0], r12d
0x1800039ac  mov     [rsp+2B8h+var_1CC], sil
0x1800039b4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800039bb  lea     rcx, [rsp+2B8h+var_1F0]; pExceptionObject
0x1800039c3  call    _CxxThrowException_0
0x1800039c9  mov     rdx, [rsp+2B8h+var_230]; bool *
0x1800039d1  mov     rcx, r14; this
0x1800039d4  call    ?GetChannelAccess@Channel@@AEAAPEAXAEA_N@Z; Channel::GetChannelAccess(bool &)
0x1800039d9  mov     [rsp+2B8h+pSecurityDescriptor], rsi
0x1800039de  mov     [rsp+2B8h+bDaclPresent], esi
0x1800039e2  mov     [rsp+2B8h+bDaclDefaulted], esi
0x1800039e6  mov     [rsp+2B8h+pDacl], rsi
0x1800039eb  test    rax, rax
0x1800039ee  jz      loc_180003AD9
0x1800039f4  mov     r9, [r14+40h]
0x1800039f8  lea     rcx, [rsp+2B8h+pSecurityDescriptor]
0x1800039fd  mov     [rsp+2B8h+var_290], rcx
0x180003a02  mov     byte ptr [rsp+2B8h+bIgnoreCase], sil
0x180003a07  mov     r9, [r9+50h]
0x180003a0b  lea     r8, unk_1800EF3F0
0x180003a12  lea     rdx, stru_18010F5E8
0x180003a19  mov     rcx, rax
0x180003a1c  call    ?TransformSDPermissions@@YAKPEAXPEAU_GENERIC_MAPPING@@QEBK0_NAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z; TransformSDPermissions(void *,_GENERIC_MAPPING *,ulong const * const,void *,bool,tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x180003a21  lea     r9, [rsp+2B8h+bDaclDefaulted]; lpbDaclDefaulted
0x180003a26  lea     r8, [rsp+2B8h+pDacl]; pDacl
0x180003a2b  lea     rdx, [rsp+2B8h+bDaclPresent]; lpbDaclPresent
0x180003a30  mov     rcx, [rsp+2B8h+pSecurityDescriptor]; pSecurityDescriptor
0x180003a35  call    cs:__imp_GetSecurityDescriptorDacl
0x180003a3b  test    eax, eax
  ... truncated ...
```
