# LdapSspiBind

- ea: `0x180017854`
- end: `0x180018552`
- name: `LdapSspiBind`
- size: `3326`
- prototype: `__int64 __usercall@<rax>(struct ldap_connection *@<rcx>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800164a0`
- `0x180049d3c`

## callees

- `0x1800037a8`
- `0x18000b440`
- `0x180012ab0`
- `0x1800147f0`
- `0x180017854`
- `0x180018cc0`
- `0x18001ce90`
- `0x180020910`
- `0x180023620`
- `0x180029810`
- `0x18002b1a4`
- `0x18002b4a4`
- `0x18002b904`
- `0x18002d530`
- `0x180031a34`
- `0x180032bd8`
- `0x180032e5c`
- `0x180032f40`
- `0x180032f8c`
- `0x180032fd8`
- `0x180034510`
- `0x18003d2fc`
- `0x18004c3d8`
- `0x18004c410`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018265`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018411`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800184f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018265`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018411`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800184f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800182a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018469`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001850e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800182a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018469`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001850e`
- `ntdll!RtlInitUnicodeString` at `0x180018445`
- `ntdll!RtlInitUnicodeString` at `0x180018445`
- `SspiCli!QueryContextAttributesW` at `0x180017e20`
- `SspiCli!QueryContextAttributesW` at `0x180017e20`
- `SspiCli!SaslInitializeSecurityContextW` at `0x180017cd4`
- `SspiCli!SaslInitializeSecurityContextW` at `0x180017cd4`

## string_xrefs

- `0x180017a38`: ` Error in processing  credentials during autoreconnect \n`
- `0x1800180d2`: `LdapSspiBind couldn't complete the                              auth token.  sErr = 0x%x\n`
- `0x1800182eb`: `LDAP rebind failed due to security error 0x%x`

## pseudocode

```c
__int64 __fastcall LdapSspiBind(
        struct ldap_connection *a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        const unsigned __int16 *a5,
        WCHAR *a6,
        __int64 a7)
{
  char v8; // r9
  _DWORD *v11; // rax
  char v12; // r12
  char v13; // r8
  char v14; // r13
  unsigned int v15; // r15d
  unsigned int v16; // esi
  const char *v17; // rdx
  unsigned int v18; // ebx
  char v19; // r12
  struct _SecBufferDesc *pInput; // rsi
  char v21; // r14
  CryptStream *v22; // rcx
  int v23; // ecx
  SECURITY_STATUS v24; // eax
  PSecBuffer pBuffers; // rax
  SECURITY_STATUS v26; // eax
  unsigned int v27; // eax
  int v28; // r9d
  unsigned int v29; // edx
  CryptStream *v30; // rcx
  _DWORD *v31; // rbx
  _DWORD *v32; // rcx
  struct _SecHandle v33; // xmm1
  __int64 v34; // rax
  const WCHAR *v35; // rdx
  __int64 v36; // rcx
  CryptStream *v37; // rax
  CryptStream *v38; // rbx
  unsigned int Reserved1[2]; // [rsp+20h] [rbp-E0h]
  unsigned int TargetDataRep[2]; // [rsp+28h] [rbp-D8h]
  struct _SecHandle *Reserved2; // [rsp+38h] [rbp-C8h]
  char v43; // [rsp+70h] [rbp-90h]
  unsigned int v44; // [rsp+74h] [rbp-8Ch]
  char v45; // [rsp+78h] [rbp-88h]
  char v46; // [rsp+79h] [rbp-87h]
  char v47; // [rsp+7Ah] [rbp-86h]
  _BYTE pfContextAttr[13]; // [rsp+7Bh] [rbp-85h] BYREF
  _DWORD *v49; // [rsp+88h] [rbp-78h] BYREF
  __int64 v50[2]; // [rsp+90h] [rbp-70h] BYREF
  char *v51; // [rsp+A0h] [rbp-60h]
  __int64 v52; // [rsp+A8h] [rbp-58h]
  struct _SecBufferDesc pOutput; // [rsp+B0h] [rbp-50h] BYREF
  _SecPkgContext_Bindings v54; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v55[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v56; // [rsp+D8h] [rbp-28h]
  SECURITY_INTEGER ptsExpiry; // [rsp+E0h] [rbp-20h] BYREF
  LPWSTR pszTargetName; // [rsp+E8h] [rbp-18h]
  __int64 v59; // [rsp+F0h] [rbp-10h]
  __int128 pBuffer; // [rsp+F8h] [rbp-8h] BYREF
  const unsigned __int16 *v61; // [rsp+108h] [rbp+8h]
  _DWORD v62[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v63; // [rsp+118h] [rbp+18h]
  unsigned int BindingsLength; // [rsp+120h] [rbp+20h]
  int v65; // [rsp+124h] [rbp+24h]
  SEC_CHANNEL_BINDINGS *Bindings; // [rsp+128h] [rbp+28h]
  struct _SecHandle phContext; // [rsp+130h] [rbp+30h] BYREF
  struct _SecHandle phCredential; // [rsp+140h] [rbp+40h] BYREF

  v8 = *((_BYTE *)a1 + 192);
  v61 = a5;
  pszTargetName = a6;
  *(_DWORD *)&pfContextAttr[1] = a3;
  phContext.dwLower = -1;
  phContext.dwUpper = -1;
  phCredential.dwLower = -1;
  phCredential.dwUpper = -1;
  v11 = (_DWORD *)((char *)a1 + 460);
  v51 = (char *)a1 + 460;
  v59 = a2;
  v45 = 1;
  v47 = 0;
  v49 = 0;
  pfContextAttr[0] = 0;
  v52 = 0;
  v54 = 0;
  if ( v8 )
  {
    v12 = 1;
  }
  else
  {
    a4 &= 0xFFFEFFF7;
    v51 = (char *)a1 + 460;
    *v11 &= 0xFFFEFFF7;
    v12 = 0;
  }
  v13 = *((_BYTE *)a1 + 193);
  if ( v13 )
  {
    v14 = 1;
  }
  else
  {
    a4 &= ~0x10u;
    v14 = 0;
    *v11 &= ~0x10u;
  }
  v43 = v12;
  v46 = v14;
  if ( *((_BYTE *)a1 + 646) )
  {
    a4 = a4 & 0xFF7EFFF7 | 0x800000;
  }
  else
  {
    if ( GlobalIntegrityDefault == 2 )
      v12 = 1;
    if ( GlobalConfidentialityDefault == 2 )
      v14 = 1;
    if ( GlobalIntegrityDefault == 1 && *((_BYTE *)a1 + 196) || GlobalIntegrityDefault == 2 )
    {
      a4 |= 0x10008u;
      v43 = 1;
    }
    if ( (unsigned int)(GlobalConfidentialityDefault - 1) <= 1 )
    {
      a4 |= 0x10u;
      v46 = 1;
    }
    if ( !v8 && !GlobalIntegrityDefault )
      a4 = a4 & 0xFF7EFFF7 | 0x800000;
    if ( !v13 && !GlobalConfidentialityDefault )
      a4 &= ~0x10u;
  }
  v15 = a4;
  v56 = 0;
  *(_WORD *)((char *)a1 + 641) = 0;
  *((_BYTE *)a1 + 643) = 0;
  *((_DWORD *)a1 + 174) = 0;
  if ( *((_BYTE *)a1 + 557) )
  {
    phCredential = (struct _SecHandle)*((_OWORD *)a1 + 11);
    if ( a7 )
    {
      v16 = ProcessAlternateCreds(a1, a2, a7, &v49);
      if ( v16 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        {
          v17 = " Error in processing  credentials during autoreconnect \n";
LABEL_32:
          LDAPClientTraceEvent(0x10000000, v17);
          return v16;
        }
        return v16;
      }
    }
    v44 = 0;
    goto LABEL_34;
  }
  if ( !a7 || (v16 = ProcessAlternateCreds(a1, a2, a7, &v49)) == 0 )
  {
    Reserved2 = &phCredential;
    TargetDataRep[1] = 0;
    Reserved1[1] = HIDWORD(v49);
    v44 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))SspiFunctionTableW->AcquireCredentialsHandleW)(
            0,
            *(_QWORD *)(a2 + 16),
            2);
    v16 = LdapConvertSecurityError(a1, v44);
    if ( v16 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
      {
        LDAPClientPrint(
          0x100000,
          "LdapSspiBind Connection 0x%x received 0x%x on                              AcquireCredentialsHandle.\n",
          (_DWORD)a1,
          v44);
        v18 = v44;
      }
      else
      {
        v18 = v44;
      }
LABEL_37:
      v19 = v43;
LABEL_38:
      if ( v54.BindingsLength && SslFunctionTableW )
      {
        if ( v54.Bindings )
          ((void (*)(void))SslFunctionTableW->FreeContextBuffer)();
        v54.Bindings = 0;
        v54.BindingsLength = 0;
      }
      if ( !pfContextAttr[0] && v16 )
        goto LABEL_220;
      if ( *((_BYTE *)a1 + 557) )
        ClearSecurityContext(a1);
      else
        CloseCredentials(a1);
      EnterCriticalSection((LPCRITICAL_SECTION)a1 + 20);
      v30 = (CryptStream *)*((_QWORD *)a1 + 88);
      if ( v30 && (*((_BYTE *)a1 + 194) || *((_BYTE *)a1 + 195)) )
      {
        CryptStream::`scalar deleting destructor'(v30, v29);
        *((_QWORD *)a1 + 88) = 0;
        *((_WORD *)a1 + 97) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 20);
      if ( v16 )
      {
LABEL_220:
        if ( *((_BYTE *)a1 + 557) )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x200) != 0 )
            LDAPClientPrint(512, "LDAP rebind failed due to security error 0x%x", v18);
          ClearSecurityContextByHandle(&phContext);
        }
        else
        {
          ClearSecurityContextByHandle(&phContext);
          CloseCredentialsByHandle(&phCredential);
        }
        if ( v16 == 49 && *((_BYTE *)a1 + 656) )
        {
          if ( v59 == SspiPackageDpa )
            LdapGlobalDpaSecurityFlags = 64;
          if ( v59 == SspiPackageSicily )
            LdapGlobalMsnSecurityFlags = 64;
        }
        if ( v45 && v47 && (v16 == 2 || v16 == 7) )
          v16 = 53;
        if ( v49 )
          ldapSecureFree(v49, 1667593036);
      }
      else
      {
        v31 = v49;
        v32 = v51;
        *((_DWORD *)a1 + 39) = *(_DWORD *)&pfContextAttr[1];
        *((_BYTE *)a1 + 195) = v46;
        *((_QWORD *)a1 + 16) = v31;
        *((_BYTE *)a1 + 194) = v19;
        if ( (v15 & 0x10008) != 0 && (*v32 & 0x10008) == 0 )
          *v32 |= 0x10008u;
        if ( (v15 & 0x10) != 0 && (*v32 & 0x10) == 0 )
          *v32 |= 0x10u;
        *(struct _SecHandle *)((char *)a1 + 216) = phContext;
        if ( !*((_BYTE *)a1 + 557) )
        {
          v33 = phCredential;
          *((_QWORD *)a1 + 26) = v52;
          *((struct _SecHandle *)a1 + 11) = v33;
        }
        if ( v31 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 88));
          v34 = *((_QWORD *)a1 + 16);
          if ( *v31 == 512 )
            v35 = *(const WCHAR **)(v34 + 40);
          else
            v35 = *(const WCHAR **)(v34 + 32);
          if ( v35 )
          {
            RtlInitUnicodeString((PUNICODE_STRING)((char *)a1 + 136), v35);
            RoundUnicodeStringMaxLength((char *)a1 + 136);
            EncodeUnicodeString(v36);
            *((_BYTE *)a1 + 152) = 1;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 88));
        }
        if ( !*((_BYTE *)a1 + 557) )
          GetCurrentLuid((_QWORD *)a1 + 21);
        if ( *((_BYTE *)a1 + 194) || *((_BYTE *)a1 + 195) )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
            LDAPClientTraceEvent(32, "Creating Cryptstream object to handle signing/sealing\n");
          v37 = (CryptStream *)CryptStream::operator new((unsigned __int64)v32);
          if ( v37 && (v38 = CryptStream::CryptStream(v37, a1, SspiFunctionTableW, 0)) != 0 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)a1 + 20);
            *((_QWORD *)a1 + 88) = v38;
            LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 20);
          }
          else
          {
            v16 = 8;
          }
        }
      }
      ldapFree(v56, 1667593036);
      return v16;
    }
LABEL_34:
    ptsExpiry.QuadPart = 0;
    *(_DWORD *)&pfContextAttr[5] = 0;
    pOutput = 0;
    *(_OWORD *)v50 = 0;
    v56 = ldapMalloc(SspiMaxTokenSize, 1667593036);
    if ( v56 )
    {
      v55[0] = SspiMaxTokenSize;
      pInput = 0;
      v55[1] = 2;
      v62[1] = 2;
      v21 = 0;
      pOutput.pBuffers = (PSecBuffer)v55;
      v22 = (CryptStream *)*((_QWORD *)a1 + 88);
      pOutput.cBuffers = 1;
      pOutput.ulVersion = 0;
      v62[0] = 0;
      v63 = 0;
      v50[1] = (__int64)v62;
      v50[0] = 0x100000000LL;
      if ( !v22 || (unsigned int)CryptStream::GetChannelBindingToken(v22, &v54) )
        goto LABEL_63;
      BindingsLength = v54.BindingsLength;
      Bindings = v54.Bindings;
      v65 = 14;
      HIDWORD(v50[0]) = 2;
      while ( 1 )
      {
        pInput = (struct _SecBufferDesc *)v50;
LABEL_63:
        v23 = *(_DWORD *)&pfContextAttr[1];
        while ( 1 )
        {
          if ( v23 == 1158 && *((_QWORD *)a1 + 83) )
          {
            v24 = SaslInitializeSecurityContextW(
                    &phCredential,
                    (PCtxtHandle)((unsigned __int64)&phContext & -(__int64)(*((_DWORD *)a1 + 174) != 0)),
                    pszTargetName,
                    a4,
                    0,
                    0x10u,
                    pInput,
                    0,
                    &phContext,
                    &pOutput,
                    (unsigned int *)&pfContextAttr[5],
                    &ptsExpiry);
          }
          else
          {
            LODWORD(Reserved2) = 0;
            TargetDataRep[0] = 16;
            Reserved1[0] = 0;
            v24 = ((__int64 (__fastcall *)(struct _SecHandle *, unsigned __int64, LPWSTR, _QWORD, _QWORD, _QWORD, struct _SecBufferDesc *, struct _SecHandle *, struct _SecHandle *, struct _SecBufferDesc *, _BYTE *, SECURITY_INTEGER *))SspiFunctionTableW->InitializeSecurityContextW)(
                    &phCredential,
                    (unsigned __int64)&phContext & -(__int64)(*((_DWORD *)a1 + 174) != 0),
                    pszTargetName,
                    a4,
                    *(_QWORD *)Reserved1,
                    *(_QWORD *)TargetDataRep,
                    pInput,
                    Reserved2,
                    &phContext,
                    &pOutput,
                    &pfContextAttr[5],
                    &ptsExpiry);
          }
          v23 = *(_DWORD *)&pfContextAttr[1];
          if ( (a4 & 0x40) != 0 )
            v21 = 1;
          v44 = v24;
          if ( *(_DWORD *)&pfContextAttr[1] != 646
            && *(_DWORD *)&pfContextAttr[1] != 8326
            && *(_DWORD *)&pfContextAttr[1] != 2182 )
          {
            break;
          }
          if ( v24 != -2146893042 || !*((_BYTE *)a1 + 656) )
            break;
          if ( v21 )
            goto LABEL_78;
          v21 = 1;
          a4 |= 0x40u;
        }
        if ( !v21 )
          goto LABEL_79;
LABEL_78:
        a4 &= ~0x40u;
        v21 = 0;
LABEL_79:
        if ( pInput )
        {
          pBuffers = pInput->pBuffers;
          if ( pBuffers->pvBuffer )
          {
            pBuffers->pvBuffer = 0;
            pInput->pBuffers->cbBuffer = 0;
            ldap_msgfree(*((LDAPMessage **)a1 + 86));
            *((_QWORD *)a1 + 86) = 0;
          }
        }
        v16 = LdapSetSspiContinueState(a1, v44);
        if ( v16 )
          goto LABEL_36;
        if ( !v47 && *(_DWORD *)&pfContextAttr[1] == 1158 )
        {
          pBuffer = 0;
          v26 = QueryContextAttributesW(&phContext, 0xCu, &pBuffer);
          if ( v26 < 0 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
              LDAPClientPrint(0x80000, "QueryContextAttributes failed with 0x%x\n", v26);
            v16 = 82;
            goto LABEL_36;
          }
          v47 = 1;
          if ( (unsigned __int8)ldapWStringsIdentical(*(PCNZWCH *)(pBuffer + 16), -1, L"Kerberos", -1) )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
              LDAPClientTraceEvent(0x80000, "wldap32:Server is capable of Kerberos\n");
            v45 = 1;
          }
          else
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
              LDAPClientPrint(0x80000, "wldap32:Server is capable of '%S'\n", *(const wchar_t **)(pBuffer + 16));
            v45 = 0;
          }
          ((void (__fastcall *)(_QWORD))SspiFunctionTableW->FreeContextBuffer)(pBuffer);
          if ( v45 )
          {
            if ( !*((_BYTE *)a1 + 197) && !*((_BYTE *)a1 + 198) )
              goto LABEL_100;
          }
          else if ( !*((_QWORD *)a1 + 83) && !*((_BYTE *)a1 + 198) && !*((_BYTE *)a1 + 197) )
          {
            v16 = 2;
            if ( *((_DWORD *)a1 + 50) == 3 )
              v16 = 7;
            goto LABEL_36;
          }
        }
        if ( *((_BYTE *)a1 + 643) )
        {
          v44 = ((__int64 (__fastcall *)(struct _SecHandle *, struct _SecBufferDesc *))SspiFunctionTableW->CompleteAuthToken)(
                  &phContext,
                  &pOutput);
          v16 = LdapConvertSecurityError(a1, v44);
          if ( v16 )
          {
            if ( !g_fTracingOn )
              goto LABEL_36;
            v18 = v44;
            if ( g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
              LDAPClientPrint(
                0x100000,
                "LdapSspiBind couldn't complete the                              auth token.  sErr = 0x%x\n",
                v44);
            goto LABEL_37;
          }
          *((_BYTE *)a1 + 643) = 0;
        }
        if ( v55[0] || v44 == 590610 )
        {
          TargetDataRep[0] = pOutput.pBuffers->cbBuffer;
          v27 = LdapExchangeOpaqueToken(
                  a1,
                  *(unsigned int *)&pfContextAttr[1],
                  *((const unsigned __int16 **)a1 + 84),
                  v61,
                  pOutput.pBuffers->pvBuffer,
                  *(size_t *)TargetDataRep,
                  (__int64)v50,
                  0,
                  0,
                  0,
                  0,
                  0,
                  0,
                  pfContextAttr);
          v16 = v27;
          if ( v27 )
          {
            if ( v27 != 14 )
              goto LABEL_36;
          }
        }
        if ( !*((_BYTE *)a1 + 641) )
        {
          v28 = *(_DWORD *)&pfContextAttr[5];
          if ( (v15 & 0x10000) != 0 && (*(_DWORD *)&pfContextAttr[5] & 0x10000) == 0
            || (v15 & 8) != 0 && (pfContextAttr[5] & 8) == 0 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
            {
              LDAPClientPrint(
                32,
                "LdapSspiBind: asked for connection supporting SspiFlags = 0x%x,                         got connection s"
                "upporting ContextAttr = 0x%x\n",
                v15,
                *(_DWORD *)&pfContextAttr[5]);
              v28 = *(_DWORD *)&pfContextAttr[5];
            }
            if ( v12 )
            {
LABEL_100:
              v16 = 53;
              goto LABEL_36;
            }
            v15 &= 0xFFFEFFF7;
            v19 = 0;
          }
          else
          {
            v19 = v43;
          }
          if ( (v28 & 0x10000) != 0 )
          {
            v15 |= 0x10000u;
            v19 = 1;
            if ( (v28 & 8) != 0 )
              v15 |= 8u;
          }
          if ( (v15 & 0x10) != 0 && (v28 & 0x10) == 0 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
            {
              LDAPClientPrint(
                32,
                "LdapSspiBind: asked for connection supporting SspiFlags = 0x%x,                         got connection s"
                "upporting ContextAttr = 0x%x\n",
                v15,
                v28);
              v28 = *(_DWORD *)&pfContextAttr[5];
            }
            if ( v14 )
            {
LABEL_154:
              v16 = 53;
              goto LABEL_155;
            }
            v15 &= ~0x10u;
            v46 = 0;
          }
          if ( *((_BYTE *)a1 + 464) && (v28 & 2) == 0 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
              LDAPClientPrint(
                0x80000,
                "LdapSspiBind: asked for connection supporting SspiFlags = 0x%x,                         got connection s"
                "upporting ContextAttr = 0x%x\n",
                v15,
                v28);
            goto LABEL_154;
          }
LABEL_155:
          v18 = v44;
          goto LABEL_38;
        }
        if ( v59 == SspiPackageDpa )
        {
          a4 |= LdapGlobalDpaSecurityFlags;
          LdapGlobalDpaSecurityFlags = 0;
        }
        if ( v59 == SspiPackageSicily )
        {
          a4 |= LdapGlobalMsnSecurityFlags;
          LdapGlobalMsnSecurityFlags = 0;
        }
        if ( !*(_QWORD *)(v50[1] + 8) || !*(_DWORD *)v50[1] )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
            LDAPClientTraceEvent(0x80000, "Expecting response credentials from remote server but got back none\n");
          v16 = 2;
          goto LABEL_36;
        }
        v55[0] = SspiMaxTokenSize;
      }
    }
    v16 = 90;
LABEL_36:
    v18 = v44;
    goto LABEL_37;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
  {
    v17 = " Error in processing alternate credentials\n";
    goto LABEL_32;
  }
  return v16;
}

```

## disassembly

```asm
0x180017854  push    rbp
0x180017856  push    rbx
0x180017857  push    rsi
0x180017858  push    rdi
0x180017859  push    r12
0x18001785b  push    r13
0x18001785d  push    r14
0x18001785f  push    r15
0x180017861  lea     rbp, [rsp-68h]
0x180017866  sub     rsp, 168h
0x18001786d  mov     rax, cs:__security_cookie
0x180017874  xor     rax, rsp
0x180017877  mov     [rbp+0A0h+var_50], rax
0x18001787b  mov     rax, [rbp+0A0h+arg_20]
0x180017882  xor     r11d, r11d
0x180017885  mov     r10, [rbp+0A0h+arg_30]
0x18001788c  mov     ebx, r9d
0x18001788f  mov     r9b, [rcx+0C0h]
0x180017896  mov     esi, 1
0x18001789b  mov     [rbp+0A0h+var_98], rax
0x18001789f  xorps   xmm0, xmm0
0x1800178a2  mov     rax, [rbp+0A0h+arg_28]
0x1800178a9  mov     r14, rdx
0x1800178ac  mov     [rbp+0A0h+pszTargetName], rax
0x1800178b0  mov     rdi, rcx
0x1800178b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800178b7  mov     dword ptr [rsp+1A0h+var_125+1], r8d
0x1800178bc  mov     [rbp+0A0h+phContext.dwLower], rax
0x1800178c0  mov     r15d, 0FFFEFFF7h
0x1800178c6  mov     [rbp+0A0h+phContext.dwUpper], rax
0x1800178ca  mov     [rbp+0A0h+phCredential.dwLower], rax
0x1800178ce  mov     [rbp+0A0h+phCredential.dwUpper], rax
0x1800178d2  lea     rax, [rcx+1CCh]
0x1800178d9  mov     [rbp+0A0h+var_100], rax
0x1800178dd  mov     [rbp+0A0h+var_B0], rdx
0x1800178e1  mov     [rsp+1A0h+var_128], sil
0x1800178e6  mov     [rsp+1A0h+var_126], r11b
0x1800178eb  mov     [rbp+0A0h+var_118], r11
0x1800178ef  mov     [rsp+1A0h+var_125], r11b
0x1800178f4  mov     [rbp+0A0h+var_F8], r11
0x1800178f8  movups  xmmword ptr [rbp+0A0h+var_E0.BindingsLength], xmm0
0x1800178fc  test    r9b, r9b
0x1800178ff  jz      short loc_180017906
0x180017901  mov     r12b, sil
0x180017904  jmp     short loc_180017913
0x180017906  and     ebx, r15d
0x180017909  mov     [rbp+0A0h+var_100], rax
0x18001790d  and     [rax], r15d
0x180017910  mov     r12b, r11b
0x180017913  mov     r8b, [rcx+0C1h]
0x18001791a  mov     ecx, 0FFFFFFEFh
0x18001791f  test    r8b, r8b
0x180017922  jz      short loc_180017929
0x180017924  mov     r13b, sil
0x180017927  jmp     short loc_180017930
0x180017929  and     ebx, ecx
0x18001792b  mov     r13b, r11b
0x18001792e  and     [rax], ecx
0x180017930  mov     [rsp+1A0h+var_130], r12b
0x180017935  mov     [rsp+1A0h+var_127], r13b
0x18001793a  cmp     [rdi+286h], r11b
0x180017941  jnz     short loc_1800179AF
0x180017943  mov     ecx, cs:?GlobalIntegrityDefault@@3W4LdapIntegrity@@A; LdapIntegrity GlobalIntegrityDefault
0x180017949  cmp     ecx, 2
0x18001794c  mov     edx, cs:?GlobalConfidentialityDefault@@3W4LdapConfidentiality@@A; LdapConfidentiality GlobalConfidentialityDefault
0x180017952  movzx   r12d, r12b
0x180017956  cmovz   r12d, esi
0x18001795a  movzx   r13d, r13b
0x18001795e  cmp     edx, 2
0x180017961  cmovz   r13d, esi
0x180017965  cmp     ecx, esi
0x180017967  jnz     short loc_180017972
0x180017969  cmp     [rdi+0C4h], r11b
0x180017970  jnz     short loc_180017977
0x180017972  cmp     ecx, 2
0x180017975  jnz     short loc_180017982
0x180017977  or      ebx, 10008h
0x18001797d  mov     [rsp+1A0h+var_130], sil
0x180017982  lea     eax, [rdx-1]
0x180017985  cmp     eax, esi
0x180017987  ja      short loc_180017991
0x180017989  or      ebx, 10h
0x18001798c  mov     [rsp+1A0h+var_127], sil
0x180017991  test    r9b, r9b
0x180017994  jnz     short loc_1800179A1
0x180017996  test    ecx, ecx
0x180017998  jnz     short loc_1800179A1
0x18001799a  and     ebx, r15d
0x18001799d  bts     ebx, 17h
0x1800179a1  test    r8b, r8b
0x1800179a4  jnz     short loc_1800179B6
0x1800179a6  test    edx, edx
0x1800179a8  jnz     short loc_1800179B6
0x1800179aa  and     ebx, 0FFFFFFEFh
0x1800179ad  jmp     short loc_1800179B6
0x1800179af  and     ebx, r15d
0x1800179b2  bts     ebx, 17h
0x1800179b6  mov     r15d, ebx
0x1800179b9  mov     [rbp+0A0h+var_C8], r11
0x1800179bd  mov     [rdi+281h], r11w
0x1800179c5  mov     [rdi+283h], r11b
0x1800179cc  mov     [rdi+2B8h], r11d
0x1800179d3  cmp     [rdi+22Dh], r11b
0x1800179da  jz      loc_180017AEB
0x1800179e0  movups  xmm0, xmmword ptr [rdi+0B0h]
0x1800179e7  movdqu  xmmword ptr [rbp+0A0h+phCredential.dwLower], xmm0
0x1800179ec  test    r10, r10
0x1800179ef  jz      short loc_180017A49
0x1800179f1  lea     r9, [rbp+0A0h+var_118]
0x1800179f5  mov     r8, r10
0x1800179f8  mov     rdx, r14
0x1800179fb  mov     rcx, rdi
0x1800179fe  call    ProcessAlternateCreds
0x180017a03  xor     r11d, r11d
0x180017a06  mov     esi, eax
0x180017a08  test    eax, eax
0x180017a0a  jz      short loc_180017A49
0x180017a0c  cmp     cs:g_fTracingOn, r11d
0x180017a13  jz      loc_18001852F
0x180017a19  cmp     cs:g_fProviderEnabled, r11d
0x180017a20  jz      loc_18001852F
0x180017a26  mov     ecx, 10000000h
0x180017a2b  test    cs:g_ulTraceFlags, rcx
0x180017a32  jz      loc_18001852F
0x180017a38  lea     rdx, aErrorInProcess_0; " Error in processing  credentials durin"...
0x180017a3f  call    LDAPClientTraceEvent
0x180017a44  jmp     loc_18001852F
0x180017a49  mov     [rsp+1A0h+var_12C], r11d
0x180017a4e  mov     ecx, cs:SspiMaxTokenSize
0x180017a54  xorps   xmm0, xmm0
0x180017a57  xorps   xmm1, xmm1
0x180017a5a  mov     qword ptr [rbp+0A0h+var_C0], r11
0x180017a5e  mov     edx, 6365734Ch
0x180017a63  mov     dword ptr [rbp+0A0h+var_125+5], r11d
0x180017a67  movups  xmmword ptr [rbp+0A0h+var_F0.ulVersion], xmm0
0x180017a6b  movups  xmmword ptr [rbp+0A0h+var_110], xmm1
0x180017a6f  call    ldapMalloc
0x180017a74  xor     r11d, r11d
0x180017a77  mov     [rbp+0A0h+var_C8], rax
0x180017a7b  test    rax, rax
0x180017a7e  jnz     loc_180017BE8
0x180017a84  lea     esi, [rax+5Ah]
0x180017a87  mov     ebx, [rsp+1A0h+var_12C]
0x180017a8b  mov     r12b, [rsp+1A0h+var_130]
0x180017a90  cmp     [rbp+0A0h+var_E0.BindingsLength], r11d
0x180017a94  jbe     short loc_180017AC2
0x180017a96  mov     rax, cs:SslFunctionTableW
0x180017a9d  test    rax, rax
0x180017aa0  jz      short loc_180017AC2
0x180017aa2  mov     rcx, [rbp+0A0h+var_E0.Bindings]
0x180017aa6  test    rcx, rcx
0x180017aa9  jz      short loc_180017ABA
0x180017aab  mov     rax, [rax+80h]
0x180017ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ab7  xor     r11d, r11d
0x180017aba  mov     [rbp+0A0h+var_E0.Bindings], r11
0x180017abe  mov     [rbp+0A0h+var_E0.BindingsLength], r11d
0x180017ac2  cmp     [rsp+1A0h+var_125], r11b
0x180017ac7  jnz     short loc_180017AD1
0x180017ac9  test    esi, esi
0x180017acb  jnz     loc_1800182C0
0x180017ad1  mov     rcx, rdi; struct ldap_connection *
0x180017ad4  cmp     [rdi+22Dh], r11b
0x180017adb  jz      loc_180018256
0x180017ae1  call    ?ClearSecurityContext@@YAXPEAUldap_connection@@@Z; ClearSecurityContext(ldap_connection *)
0x180017ae6  jmp     loc_18001825B
0x180017aeb  test    r10, r10
0x180017aee  jz      short loc_180017B43
0x180017af0  lea     r9, [rbp+0A0h+var_118]
0x180017af4  mov     r8, r10
0x180017af7  mov     rdx, r14
0x180017afa  mov     rcx, rdi
0x180017afd  call    ProcessAlternateCreds
0x180017b02  xor     r11d, r11d
0x180017b05  mov     esi, eax
0x180017b07  test    eax, eax
0x180017b09  jz      short loc_180017B43
0x180017b0b  cmp     cs:g_fTracingOn, r11d
0x180017b12  jz      loc_18001852F
0x180017b18  cmp     cs:g_fProviderEnabled, r11d
0x180017b1f  jz      loc_18001852F
0x180017b25  mov     ecx, 10000000h
0x180017b2a  test    cs:g_ulTraceFlags, rcx
0x180017b31  jz      loc_18001852F
0x180017b37  lea     rdx, aErrorInProcess; " Error in processing alternate credenti"...
0x180017b3e  jmp     loc_180017A3F
0x180017b43  mov     rax, cs:SspiFunctionTableW
0x180017b4a  lea     rcx, [rbp+0A0h+var_F8]
0x180017b4e  mov     rdx, [r14+10h]
0x180017b52  xor     r9d, r9d
0x180017b55  mov     [rsp+1A0h+phNewContext], rcx
0x180017b5a  lea     rcx, [rbp+0A0h+phCredential]
0x180017b5e  mov     qword ptr [rsp+1A0h+Reserved2], rcx
0x180017b63  mov     rcx, [rbp+0A0h+var_118]
0x180017b67  mov     rax, [rax+18h]
0x180017b6b  lea     r8d, [r9+2]
0x180017b6f  mov     [rsp+1A0h+pInput], r11
0x180017b74  mov     qword ptr [rsp+1A0h+TargetDataRep], r11
0x180017b79  mov     qword ptr [rsp+1A0h+Reserved1], rcx
0x180017b7e  xor     ecx, ecx
0x180017b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b85  mov     edx, eax
0x180017b87  mov     [rsp+1A0h+var_12C], eax
0x180017b8b  mov     rcx, rdi
0x180017b8e  mov     r14d, eax
0x180017b91  call    LdapConvertSecurityError
0x180017b96  xor     r11d, r11d
0x180017b99  mov     esi, eax
0x180017b9b  test    eax, eax
0x180017b9d  jz      loc_180017A4E
0x180017ba3  cmp     cs:g_fTracingOn, r11d
0x180017baa  jz      short loc_180017BE0
0x180017bac  cmp     cs:g_fProviderEnabled, r11d
0x180017bb3  jz      short loc_180017BE0
0x180017bb5  mov     ecx, 100000h
0x180017bba  test    cs:g_ulTraceFlags, rcx
0x180017bc1  jz      short loc_180017BE0
0x180017bc3  mov     r9d, r14d
0x180017bc6  lea     rdx, aLdapsspibindCo; "LdapSspiBind Connection 0x%x received 0"...
0x180017bcd  mov     r8, rdi
0x180017bd0  call    LDAPClientPrint
0x180017bd5  mov     ebx, r14d
0x180017bd8  xor     r11d, r11d
0x180017bdb  jmp     loc_180017A8B
0x180017be0  mov     ebx, r14d
0x180017be3  jmp     loc_180017A8B
0x180017be8  mov     eax, cs:SspiMaxTokenSize
0x180017bee  mov     ecx, 2
0x180017bf3  mov     [rbp+0A0h+var_D0], eax
0x180017bf6  mov     rsi, r11
0x180017bf9  lea     rax, [rbp+0A0h+var_D0]
0x180017bfd  mov     [rbp+0A0h+var_CC], ecx
0x180017c00  mov     [rbp+0A0h+var_8C], ecx
0x180017c03  mov     r14b, r11b
0x180017c06  lea     edx, [rcx-1]
0x180017c09  mov     [rbp+0A0h+var_F0.pBuffers], rax
0x180017c0d  mov     rcx, [rdi+2C0h]; this
0x180017c14  lea     rax, [rbp+0A0h+var_90]
0x180017c18  mov     [rbp+0A0h+var_F0.cBuffers], edx
0x180017c1b  mov     [rbp+0A0h+var_F0.ulVersion], r11d
0x180017c1f  mov     [rbp+0A0h+var_90], r11d
0x180017c23  mov     [rbp+0A0h+var_88], r11
0x180017c27  mov     dword ptr [rbp+0A0h+var_110+4], edx
0x180017c2a  mov     [rbp+0A0h+var_110+8], rax
0x180017c2e  mov     dword ptr [rbp+0A0h+var_110], r11d
0x180017c32  test    rcx, rcx
0x180017c35  jz      short loc_180017C67
0x180017c37  lea     rdx, [rbp+0A0h+var_E0]; struct _SecPkgContext_Bindings *
0x180017c3b  call    ?GetChannelBindingToken@CryptStream@@QEAAJPEAU_SecPkgContext_Bindings@@@Z; CryptStream::GetChannelBindingToken(_SecPkgContext_Bindings *)
0x180017c40  xor     r11d, r11d
0x180017c43  test    eax, eax
0x180017c45  jnz     short loc_180017C67
0x180017c47  mov     eax, [rbp+0A0h+var_E0.BindingsLength]
0x180017c4a  mov     [rbp+0A0h+var_80], eax
0x180017c4d  mov     rax, [rbp+0A0h+var_E0.Bindings]
0x180017c51  mov     [rbp+0A0h+var_78], rax
0x180017c55  mov     [rbp+0A0h+var_7C], 0Eh
0x180017c5c  mov     dword ptr [rbp+0A0h+var_110+4], 2
0x180017c63  lea     rsi, [rbp+0A0h+var_110]
0x180017c67  mov     ecx, dword ptr [rsp+1A0h+var_125+1]
0x180017c6b  cmp     ecx, 486h
0x180017c71  jnz     short loc_180017CE2
0x180017c73  cmp     [rdi+298h], r11
0x180017c7a  jz      short loc_180017CE2
0x180017c7c  mov     eax, [rdi+2B8h]
0x180017c82  lea     rcx, [rbp+0A0h+phCredential]; phCredential
0x180017c86  mov     r8, [rbp+0A0h+pszTargetName]; pszTargetName
0x180017c8a  neg     eax
0x180017c8c  lea     rax, [rbp+0A0h+phContext]
0x180017c90  mov     r9d, ebx; fContextReq
0x180017c93  sbb     rdx, rdx
0x180017c96  and     rdx, rax; phContext
0x180017c99  lea     rax, [rbp+0A0h+var_C0]
0x180017c9d  mov     [rsp+1A0h+ptsExpiry], rax; ptsExpiry
0x180017ca2  lea     rax, [rbp+0A0h+var_125+5]
0x180017ca6  mov     [rsp+1A0h+pfContextAttr], rax; pfContextAttr
0x180017cab  lea     rax, [rbp+0A0h+var_F0]
0x180017caf  mov     [rsp+1A0h+pOutput], rax; pOutput
0x180017cb4  lea     rax, [rbp+0A0h+phContext]
0x180017cb8  mov     [rsp+1A0h+phNewContext], rax; phNewContext
0x180017cbd  mov     [rsp+1A0h+Reserved2], r11d; Reserved2
0x180017cc2  mov     [rsp+1A0h+pInput], rsi; pInput
0x180017cc7  mov     [rsp+1A0h+TargetDataRep], 10h; TargetDataRep
0x180017ccf  mov     [rsp+1A0h+Reserved1], r11d; Reserved1
0x180017cd4  call    cs:__imp_SaslInitializeSecurityContextW
0x180017cdb  nop     dword ptr [rax+rax+00h]
0x180017ce0  jmp     short loc_180017D4A
0x180017ce2  mov     eax, [rdi+2B8h]
0x180017ce8  lea     rcx, [rbp+0A0h+var_C0]
0x180017cec  mov     r8, [rbp+0A0h+pszTargetName]
0x180017cf0  neg     eax
0x180017cf2  mov     [rsp+1A0h+ptsExpiry], rcx
0x180017cf7  lea     rax, [rbp+0A0h+phContext]
0x180017cfb  lea     rcx, [rbp+0A0h+var_125+5]
0x180017cff  sbb     rdx, rdx
0x180017d02  mov     [rsp+1A0h+pfContextAttr], rcx
0x180017d07  and     rdx, rax
0x180017d0a  mov     rax, cs:SspiFunctionTableW
0x180017d11  lea     rcx, [rbp+0A0h+var_F0]
0x180017d15  mov     [rsp+1A0h+pOutput], rcx
  ... truncated ...
```
