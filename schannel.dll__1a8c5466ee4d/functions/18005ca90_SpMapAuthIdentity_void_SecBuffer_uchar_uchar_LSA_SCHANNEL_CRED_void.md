# SpMapAuthIdentity(void *,_SecBuffer *,uchar,uchar,LSA_SCHANNEL_CRED *,void *)

- ea: `0x18005ca90`
- end: `0x18005cf8a`
- name: `?SpMapAuthIdentity@@YAKPEAXPEAU_SecBuffer@@EEPEAULSA_SCHANNEL_CRED@@0@Z`
- size: `1274`
- prototype: `unsigned int __fastcall(void *, struct _SecBuffer *, unsigned __int8, unsigned __int8, struct LSA_SCHANNEL_CRED *, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002b800`

## callees

- `0x180014240`
- `0x180021da8`
- `0x180021eb0`
- `0x18003f740`
- `0x180057c8c`
- `0x1800597b0`
- `0x18005bdc4`
- `0x18005c3e0`
- `0x18005ca90`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cf0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cf37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cf0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cf37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd2d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005cf62`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005cf62`
- `ntdll!RtlInitUnicodeString` at `0x18005cb52`
- `ntdll!RtlInitUnicodeString` at `0x18005cb5e`
- `ntdll!RtlInitUnicodeString` at `0x18005cb52`
- `ntdll!RtlInitUnicodeString` at `0x18005cb5e`
- `CRYPT32!CertOpenStore` at `0x18005cd1f`
- `CRYPT32!CertOpenStore` at `0x18005cd1f`
- `CRYPT32!CertCloseStore` at `0x18005cf56`
- `CRYPT32!CertCloseStore` at `0x18005cf56`
- `CRYPT32!CertFreeCertificateContext` at `0x18005cead`
- `CRYPT32!CertFreeCertificateContext` at `0x18005cead`
- `CRYPT32!CertFindCertificateInStore` at `0x18005cd6f`
- `CRYPT32!CertFindCertificateInStore` at `0x18005cd6f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005cdaf`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005cde1`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005cdaf`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005cde1`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x18005ccdc`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x18005ccdc`
- `api-ms-win-security-credentials-l1-1-0!CredIsMarshaledCredentialW` at `0x18005ccbc`
- `api-ms-win-security-credentials-l1-1-0!CredIsMarshaledCredentialW` at `0x18005ccbc`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18005cf46`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18005cf46`

## pseudocode

```c
__int64 __fastcall SpMapAuthIdentity(
        void *a1,
        struct _SecBuffer *a2,
        char a3,
        char a4,
        struct LSA_SCHANNEL_CRED *a5,
        void *a6)
{
  HCERTSTORE v7; // r14
  int v10; // esi
  _OWORD *v11; // rdi
  DWORD LastError; // ebx
  __int64 (__fastcall *v13)(_QWORD, __int64, _OWORD *, void *); // rax
  unsigned __int16 *v14; // rcx
  unsigned __int8 v15; // si
  CCipherMill *v16; // rcx
  __int64 v17; // rdx
  unsigned __int16 *v18; // rcx
  const CERT_CONTEXT *CertificateInStore; // rax
  const CERT_CONTEXT *v20; // r12
  void *v21; // rsi
  _QWORD *pvBuffer; // rdx
  void *v23; // rax
  unsigned int v24; // eax
  unsigned __int64 v25; // rcx
  unsigned int v26; // eax
  __int64 v27; // rbx
  __int64 v28; // r15
  const CERT_CONTEXT **v29; // rax
  PWSTR Buffer; // rcx
  __int64 Length; // rax
  DWORD pcbData[2]; // [rsp+38h] [rbp-81h] BYREF
  _CRED_MARSHAL_TYPE CredType; // [rsp+40h] [rbp-79h] BYREF
  int v37; // [rsp+44h] [rbp-75h] BYREF
  PVOID Credential; // [rsp+48h] [rbp-71h] BYREF
  struct _UNICODE_STRING v39; // [rsp+50h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-59h] BYREF
  __int128 pvFindPara; // [rsp+70h] [rbp-49h] BYREF
  _OWORD v42[3]; // [rsp+80h] [rbp-39h] BYREF

  *(_QWORD *)pcbData = a6;
  CredType = 0;
  v7 = 0;
  Credential = 0;
  v37 = 0;
  memset(v42, 0, 44);
  DestinationString = 0;
  v39 = 0;
  pvFindPara = 0;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
  if ( a1 && a2 && a5 )
  {
    RtlInitUnicodeString(&DestinationString, 0);
    RtlInitUnicodeString(&v39, 0);
    v10 = 72;
    v11 = SPExternalAlloc(0x48u);
    if ( !v11 )
    {
      LastError = 14;
      goto LABEL_65;
    }
    v13 = *(__int64 (__fastcall **)(_QWORD, __int64, _OWORD *, void *))(LsaTable + 80);
    if ( a4 )
    {
      LastError = v13(0, 44, v42, a1);
      if ( !LastError )
      {
        *(_DWORD *)v11 = v42[0];
        if ( DWORD1(v42[0]) >= 0x48 )
          v10 = DWORD1(v42[0]);
        *((_DWORD *)v11 + 1) = v10;
        *((_DWORD *)v11 + 4) = HIDWORD(v42[0]);
        *((_QWORD *)v11 + 1) = DWORD2(v42[0]);
        *((_DWORD *)v11 + 8) = DWORD1(v42[1]);
        *((_QWORD *)v11 + 3) = LODWORD(v42[1]);
        *((_DWORD *)v11 + 12) = HIDWORD(v42[1]);
        *((_QWORD *)v11 + 5) = DWORD2(v42[1]);
        *((_DWORD *)v11 + 13) = v42[2];
        *((_DWORD *)v11 + 16) = DWORD2(v42[2]);
        *((_QWORD *)v11 + 7) = DWORD1(v42[2]);
LABEL_15:
        v14 = (unsigned __int16 *)*((_QWORD *)v11 + 1);
        v15 = (*((_BYTE *)v11 + 52) & 1) == 0;
        if ( v14 )
        {
          LastError = CopyClientString(v14, *((_DWORD *)v11 + 4), (*((_BYTE *)v11 + 52) & 1) == 0, &DestinationString);
          if ( LastError )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_63;
            }
            v17 = 35;
            goto LABEL_20;
          }
        }
        v18 = (unsigned __int16 *)*((_QWORD *)v11 + 5);
        if ( v18 )
        {
          LastError = CopyClientString(v18, *((_DWORD *)v11 + 12), v15, &v39);
          if ( LastError )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_63;
            }
            v17 = 36;
LABEL_20:
            WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, LastError);
            goto LABEL_63;
          }
        }
        if ( !CredIsMarshaledCredentialW(DestinationString.Buffer)
          || !CredUnmarshalCredentialW(DestinationString.Buffer, &CredType, &Credential)
          || CredType != CertCredential )
        {
          LastError = -2146893043;
          goto LABEL_63;
        }
        LastError = SslImpersonateClient(*(void **)pcbData, &v37);
        if ( LastError )
          goto LABEL_63;
        v7 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x10004u, L"MY");
        if ( !v7
          || (*((_QWORD *)&pvFindPara + 1) = (char *)Credential + 4,
              LODWORD(pvFindPara) = 20,
              CertificateInStore = CertFindCertificateInStore(v7, 1u, 0, 0x10000u, &pvFindPara, 0),
              (v20 = CertificateInStore) == 0) )
        {
          LastError = GetLastError();
          goto LABEL_63;
        }
        v21 = 0;
        if ( a3 )
        {
          pvBuffer = a2->pvBuffer;
          if ( !pvBuffer )
          {
            pcbData[0] = 0;
            if ( CertGetCertificateContextProperty(CertificateInStore, 2u, 0, pcbData) )
            {
              v23 = SPExternalAlloc(pcbData[0]);
              v21 = v23;
              if ( v23 )
              {
                if ( CertGetCertificateContextProperty(v20, 2u, v23, pcbData) )
                {
                  v24 = RemotelyOpenClientKeyHandle(
                          *(const unsigned __int16 **)v21,
                          *((const unsigned __int16 **)v21 + 1),
                          (unsigned __int8 *)Credential + 4,
                          *((_DWORD *)v21 + 10),
                          *((_DWORD *)v21 + 4),
                          *((_DWORD *)v21 + 5));
                  LastError = 590610;
                  if ( v24 )
                    LastError = v24;
                  goto LABEL_60;
                }
              }
            }
            goto LABEL_38;
          }
          if ( a2->cbBuffer < 0x14 )
            goto LABEL_38;
          v25 = *pvBuffer - *(_QWORD *)((char *)Credential + 4);
          if ( *pvBuffer == *(_QWORD *)((char *)Credential + 4) )
          {
            v25 = pvBuffer[1] - *(_QWORD *)((char *)Credential + 12);
            if ( !v25 )
              v25 = *((unsigned int *)pvBuffer + 4) - (unsigned __int64)*((unsigned int *)Credential + 5);
          }
          if ( v25 )
            goto LABEL_38;
          v26 = a2->cbBuffer - 20;
          if ( a4 )
          {
            if ( v26 < 8 )
            {
LABEL_50:
              LastError = -2146893052;
              goto LABEL_60;
            }
            v27 = *((unsigned int *)pvBuffer + 5);
            v28 = *((unsigned int *)pvBuffer + 6);
          }
          else
          {
            if ( v26 < 0x10 )
              goto LABEL_50;
            v27 = *(_QWORD *)((char *)pvBuffer + 20);
            v28 = *(_QWORD *)((char *)pvBuffer + 28);
          }
          if ( !v27 && !v28 )
          {
LABEL_38:
            LastError = -2146893043;
            goto LABEL_60;
          }
        }
        else
        {
          v27 = 0;
          v28 = 0;
        }
        v29 = (const CERT_CONTEXT **)SPExternalAlloc(0x38u);
        *((_QWORD *)a5 + 1) = v29;
        if ( v29 )
        {
          *v29 = v20;
          *(_QWORD *)(*((_QWORD *)a5 + 1) + 8LL) = v39.Buffer;
          *(_QWORD *)(*((_QWORD *)a5 + 1) + 32LL) = v27;
          LastError = 0;
          *(_QWORD *)(*((_QWORD *)a5 + 1) + 16LL) = v28;
          *(_BYTE *)(*((_QWORD *)a5 + 1) + 24LL) = 0;
          v39.Buffer = 0;
          *((_DWORD *)a5 + 1) = 1;
          goto LABEL_63;
        }
        LastError = 14;
LABEL_60:
        CertFreeCertificateContext(v20);
        if ( v21 )
          SPExternalFree(v21);
      }
    }
    else
    {
      LastError = v13(0, 72, v11, a1);
      if ( !LastError )
        goto LABEL_15;
    }
LABEL_63:
    SPExternalFree(v11);
    goto LABEL_65;
  }
  LastError = 87;
LABEL_65:
  if ( DestinationString.Buffer )
    LocalFree(DestinationString.Buffer);
  Buffer = v39.Buffer;
  if ( v39.Buffer )
  {
    Length = v39.Length;
    if ( v39.Length )
    {
      do
      {
        *(_BYTE *)Buffer = 0;
        Buffer = (PWSTR)((char *)Buffer + 1);
        --Length;
      }
      while ( Length );
      Buffer = v39.Buffer;
    }
    LocalFree(Buffer);
  }
  if ( Credential )
    CredFree(Credential);
  if ( v7 )
    CertCloseStore(v7, 0);
  if ( v37 )
    RevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x18005ca90  push    rbp
0x18005ca92  push    rbx
0x18005ca93  push    rsi
0x18005ca94  push    rdi
0x18005ca95  push    r12
0x18005ca97  push    r13
0x18005ca99  push    r14
0x18005ca9b  push    r15
0x18005ca9d  lea     rbp, [rsp-0Fh]
0x18005caa2  sub     rsp, 0C8h
0x18005caa9  mov     rax, cs:__security_cookie
0x18005cab0  xor     rax, rsp
0x18005cab3  mov     [rbp+47h+var_50], rax
0x18005cab7  mov     rax, [rbp+47h+arg_28]
0x18005cabb  xorps   xmm0, xmm0
0x18005cabe  mov     r13, [rbp+47h+arg_20]
0x18005cac2  xorps   xmm1, xmm1
0x18005cac5  mov     qword ptr [rsp+100h+pcbData], rax
0x18005caca  mov     r12b, r9b
0x18005cacd  xor     eax, eax
0x18005cacf  mov     [rsp+100h+var_CF], r9b
0x18005cad4  movups  [rbp+47h+var_70], xmm0
0x18005cad8  mov     [rbp+47h+CredType], eax
0x18005cadb  xor     r14d, r14d
0x18005cade  mov     [rbp+47h+Credential], rax
0x18005cae2  mov     r15, rdx
0x18005cae5  mov     [rbp+47h+var_BC], eax
0x18005cae8  mov     rbx, rcx
0x18005caeb  mov     [rsp+100h+var_D0], r8b
0x18005caf0  movups  [rbp+47h+var_80], xmm0
0x18005caf4  movups  [rbp+47h+var_70+0Ch], xmm0
0x18005caf8  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x18005cafc  movups  xmmword ptr [rbp+47h+var_B0.Length], xmm1
0x18005cb00  movups  [rbp+47h+pvFindPara], xmm0
0x18005cb04  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cb0b  lea     rax, WPP_GLOBAL_Control
0x18005cb12  cmp     rcx, rax
0x18005cb15  jz      short loc_18005CB31
0x18005cb17  test    byte ptr [rcx+1Ch], 4
0x18005cb1b  jz      short loc_18005CB31
0x18005cb1d  mov     rcx, [rcx+10h]
0x18005cb21  lea     edx, [r14+22h]
0x18005cb25  lea     r8, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18005cb2c  call    WPP_SF_
0x18005cb31  test    rbx, rbx
0x18005cb34  jz      loc_18005CF01
0x18005cb3a  test    r15, r15
0x18005cb3d  jz      loc_18005CF01
0x18005cb43  test    r13, r13
0x18005cb46  jz      loc_18005CF01
0x18005cb4c  xor     edx, edx; SourceString
0x18005cb4e  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x18005cb52  call    cs:__imp_RtlInitUnicodeString
0x18005cb58  xor     edx, edx; SourceString
0x18005cb5a  lea     rcx, [rbp+47h+var_B0]; DestinationString
0x18005cb5e  call    cs:__imp_RtlInitUnicodeString
0x18005cb64  mov     esi, 48h ; 'H'
0x18005cb69  mov     ecx, esi; uBytes
0x18005cb6b  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18005cb70  mov     rdi, rax
0x18005cb73  test    rax, rax
0x18005cb76  jnz     short loc_18005CB80
0x18005cb78  lea     ebx, [rsi-3Ah]
0x18005cb7b  jmp     loc_18005CF06
0x18005cb80  mov     rax, cs:LsaTable
0x18005cb87  xor     ecx, ecx
0x18005cb89  mov     r9, rbx
0x18005cb8c  mov     rax, [rax+50h]
0x18005cb90  test    r12b, r12b
0x18005cb93  jz      short loc_18005CBF7
0x18005cb95  lea     r8, [rbp+47h+var_80]
0x18005cb99  lea     edx, [rcx+2Ch]
0x18005cb9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cba1  mov     ebx, eax
0x18005cba3  test    eax, eax
0x18005cba5  jnz     loc_18005CEF7
0x18005cbab  mov     eax, dword ptr [rbp+47h+var_80]
0x18005cbae  mov     [rdi], eax
0x18005cbb0  cmp     dword ptr [rbp+47h+var_80+4], esi
0x18005cbb3  jb      short loc_18005CBB8
0x18005cbb5  mov     esi, dword ptr [rbp+47h+var_80+4]
0x18005cbb8  mov     [rdi+4], esi
0x18005cbbb  mov     eax, dword ptr [rbp+47h+var_80+0Ch]
0x18005cbbe  mov     [rdi+10h], eax
0x18005cbc1  mov     eax, dword ptr [rbp+47h+var_80+8]
0x18005cbc4  mov     [rdi+8], rax
0x18005cbc8  mov     eax, dword ptr [rbp+47h+var_70+4]
0x18005cbcb  mov     [rdi+20h], eax
0x18005cbce  mov     eax, dword ptr [rbp+47h+var_70]
0x18005cbd1  mov     [rdi+18h], rax
0x18005cbd5  mov     eax, dword ptr [rbp+47h+var_70+0Ch]
0x18005cbd8  mov     [rdi+30h], eax
0x18005cbdb  mov     eax, dword ptr [rbp+47h+var_70+8]
0x18005cbde  mov     [rdi+28h], rax
0x18005cbe2  mov     eax, [rbp+47h+var_60]
0x18005cbe5  mov     [rdi+34h], eax
0x18005cbe8  mov     eax, [rbp+47h+var_58]
0x18005cbeb  mov     [rdi+40h], eax
0x18005cbee  mov     eax, [rbp+47h+var_5C]
0x18005cbf1  mov     [rdi+38h], rax
0x18005cbf5  jmp     short loc_18005CC0B
0x18005cbf7  mov     r8, rdi
0x18005cbfa  mov     edx, esi
0x18005cbfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc01  mov     ebx, eax
0x18005cc03  test    eax, eax
0x18005cc05  jnz     loc_18005CEF7
0x18005cc0b  mov     sil, [rdi+34h]
0x18005cc0f  mov     rcx, [rdi+8]; unsigned __int16 *
0x18005cc13  not     sil
0x18005cc16  and     sil, 1
0x18005cc1a  test    rcx, rcx
0x18005cc1d  jz      short loc_18005CC72
0x18005cc1f  mov     edx, [rdi+10h]; unsigned int
0x18005cc22  lea     r9, [rbp+47h+DestinationString]; struct _UNICODE_STRING *
0x18005cc26  mov     r8b, sil; unsigned __int8
0x18005cc29  call    ?CopyClientString@@YAJPEAGKEPEAU_UNICODE_STRING@@@Z; CopyClientString(ushort *,ulong,uchar,_UNICODE_STRING *)
0x18005cc2e  mov     ebx, eax
0x18005cc30  test    eax, eax
0x18005cc32  jz      short loc_18005CC72
0x18005cc34  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cc3b  lea     rax, WPP_GLOBAL_Control
0x18005cc42  cmp     rcx, rax
0x18005cc45  jz      loc_18005CEF7
0x18005cc4b  test    byte ptr [rcx+1Ch], 1
0x18005cc4f  jz      loc_18005CEF7
0x18005cc55  mov     edx, 23h ; '#'
0x18005cc5a  mov     rcx, [rcx+10h]
0x18005cc5e  lea     r8, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18005cc65  mov     r9d, ebx
0x18005cc68  call    WPP_SF_d
0x18005cc6d  jmp     loc_18005CEF7
0x18005cc72  mov     rcx, [rdi+28h]; unsigned __int16 *
0x18005cc76  test    rcx, rcx
0x18005cc79  jz      short loc_18005CCB8
0x18005cc7b  mov     edx, [rdi+30h]; unsigned int
0x18005cc7e  lea     r9, [rbp+47h+var_B0]; struct _UNICODE_STRING *
0x18005cc82  mov     r8b, sil; unsigned __int8
0x18005cc85  call    ?CopyClientString@@YAJPEAGKEPEAU_UNICODE_STRING@@@Z; CopyClientString(ushort *,ulong,uchar,_UNICODE_STRING *)
0x18005cc8a  mov     ebx, eax
0x18005cc8c  test    eax, eax
0x18005cc8e  jz      short loc_18005CCB8
0x18005cc90  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cc97  lea     rax, WPP_GLOBAL_Control
0x18005cc9e  cmp     rcx, rax
0x18005cca1  jz      loc_18005CEF7
0x18005cca7  test    byte ptr [rcx+1Ch], 1
0x18005ccab  jz      loc_18005CEF7
0x18005ccb1  mov     edx, 24h ; '$'
0x18005ccb6  jmp     short loc_18005CC5A
0x18005ccb8  mov     rcx, [rbp+47h+DestinationString.Buffer]; MarshaledCredential
0x18005ccbc  call    cs:__imp_CredIsMarshaledCredentialW
0x18005ccc2  test    eax, eax
0x18005ccc4  jnz     short loc_18005CCD0
0x18005ccc6  mov     ebx, 8009030Dh
0x18005cccb  jmp     loc_18005CEF7
0x18005ccd0  mov     rcx, [rbp+47h+DestinationString.Buffer]; MarshaledCredential
0x18005ccd4  lea     r8, [rbp+47h+Credential]; Credential
0x18005ccd8  lea     rdx, [rbp+47h+CredType]; CredType
0x18005ccdc  call    cs:__imp_CredUnmarshalCredentialW
0x18005cce2  test    eax, eax
0x18005cce4  jz      short loc_18005CCC6
0x18005cce6  cmp     [rbp+47h+CredType], 1
0x18005ccea  jnz     short loc_18005CCC6
0x18005ccec  mov     rcx, qword ptr [rsp+100h+pcbData]; void *
0x18005ccf1  lea     rdx, [rbp+47h+var_BC]; int *
0x18005ccf5  call    ?SslImpersonateClient@@YAKPEAXPEAH@Z; SslImpersonateClient(void *,int *)
0x18005ccfa  mov     ebx, eax
0x18005ccfc  test    eax, eax
0x18005ccfe  jnz     loc_18005CEF7
0x18005cd04  lea     rax, aMy; "MY"
0x18005cd0b  mov     r9d, 10004h; dwFlags
0x18005cd11  xor     r8d, r8d; hCryptProv
0x18005cd14  mov     [rsp+100h+pvPara], rax; pvPara
0x18005cd19  lea     edx, [rbx+1]; dwEncodingType
0x18005cd1c  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x18005cd1f  call    cs:__imp_CertOpenStore
0x18005cd25  mov     r14, rax
0x18005cd28  test    rax, rax
0x18005cd2b  jnz     short loc_18005CD3A
0x18005cd2d  call    cs:__imp_GetLastError
0x18005cd33  mov     ebx, eax
0x18005cd35  jmp     loc_18005CEF7
0x18005cd3a  mov     rax, [rbp+47h+Credential]
0x18005cd3e  xor     r8d, r8d; dwFindFlags
0x18005cd41  add     rax, 4
0x18005cd45  mov     [rsp+100h+pPrevCertContext], 0; pPrevCertContext
0x18005cd4e  mov     qword ptr [rbp+47h+pvFindPara+8], rax
0x18005cd52  mov     r9d, 10000h; dwFindType
0x18005cd58  lea     rax, [rbp+47h+pvFindPara]
0x18005cd5c  mov     dword ptr [rbp+47h+pvFindPara], 14h
0x18005cd63  lea     edx, [r8+1]; dwCertEncodingType
0x18005cd67  mov     [rsp+100h+pvPara], rax; pvFindPara
0x18005cd6c  mov     rcx, r14; hCertStore
0x18005cd6f  call    cs:__imp_CertFindCertificateInStore
0x18005cd75  mov     r12, rax
0x18005cd78  test    rax, rax
0x18005cd7b  jz      short loc_18005CD2D
0x18005cd7d  xor     esi, esi
0x18005cd7f  xor     r9d, r9d
0x18005cd82  cmp     [rsp+100h+var_D0], r9b
0x18005cd87  jz      loc_18005CE8E
0x18005cd8d  mov     rdx, [r15+8]
0x18005cd91  test    rdx, rdx
0x18005cd94  jnz     loc_18005CE20
0x18005cd9a  mov     [rsp+100h+pcbData], r9d
0x18005cd9f  lea     ebx, [rsi+2]
0x18005cda2  mov     edx, ebx; dwPropId
0x18005cda4  lea     r9, [rsp+100h+pcbData]; pcbData
0x18005cda9  xor     r8d, r8d; pvData
0x18005cdac  mov     rcx, rax; pCertContext
0x18005cdaf  call    cs:__imp_CertGetCertificateContextProperty
0x18005cdb5  test    eax, eax
0x18005cdb7  jz      short loc_18005CDCA
0x18005cdb9  mov     ecx, [rsp+100h+pcbData]; uBytes
0x18005cdbd  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18005cdc2  mov     rsi, rax
0x18005cdc5  test    rax, rax
0x18005cdc8  jnz     short loc_18005CDD4
0x18005cdca  mov     ebx, 8009030Dh
0x18005cdcf  jmp     loc_18005CEAA
0x18005cdd4  lea     r9, [rsp+100h+pcbData]; pcbData
0x18005cdd9  mov     r8, rsi; pvData
0x18005cddc  mov     edx, ebx; dwPropId
0x18005cdde  mov     rcx, r12; pCertContext
0x18005cde1  call    cs:__imp_CertGetCertificateContextProperty
0x18005cde7  test    eax, eax
0x18005cde9  jz      short loc_18005CDCA
0x18005cdeb  mov     eax, [rsi+14h]
0x18005cdee  mov     r8, [rbp+47h+Credential]
0x18005cdf2  mov     r9d, [rsi+28h]; unsigned int
0x18005cdf6  add     r8, 4; unsigned __int8 *
0x18005cdfa  mov     rdx, [rsi+8]; unsigned __int16 *
0x18005cdfe  mov     rcx, [rsi]; unsigned __int16 *
0x18005ce01  mov     dword ptr [rsp+100h+pPrevCertContext], eax; unsigned int
0x18005ce05  mov     eax, [rsi+10h]
0x18005ce08  mov     dword ptr [rsp+100h+pvPara], eax; unsigned int
0x18005ce0c  call    ?RemotelyOpenClientKeyHandle@@YAKPEBG0PEAEKKK@Z; RemotelyOpenClientKeyHandle(ushort const *,ushort const *,uchar *,ulong,ulong,ulong)
0x18005ce11  test    eax, eax
0x18005ce13  mov     ebx, 90312h
0x18005ce18  cmovnz  ebx, eax
0x18005ce1b  jmp     loc_18005CEAA
0x18005ce20  mov     r8d, [r15]
0x18005ce23  cmp     r8d, 14h
0x18005ce27  jb      short loc_18005CDCA
0x18005ce29  mov     rax, [rbp+47h+Credential]
0x18005ce2d  mov     rcx, [rdx]
0x18005ce30  sub     rcx, [rax+4]
0x18005ce34  jnz     short loc_18005CE49
0x18005ce36  mov     rcx, [rdx+8]
0x18005ce3a  sub     rcx, [rax+0Ch]
0x18005ce3e  jnz     short loc_18005CE49
0x18005ce40  mov     ecx, [rdx+10h]
0x18005ce43  mov     eax, [rax+14h]
0x18005ce46  sub     rcx, rax
0x18005ce49  test    rcx, rcx
0x18005ce4c  jnz     loc_18005CDCA
0x18005ce52  lea     eax, [r8-14h]
0x18005ce56  cmp     [rsp+100h+var_CF], r9b
0x18005ce5b  jz      short loc_18005CE72
0x18005ce5d  cmp     eax, 8
0x18005ce60  jnb     short loc_18005CE69
0x18005ce62  mov     ebx, 80090304h
0x18005ce67  jmp     short loc_18005CEAA
0x18005ce69  mov     ebx, [rdx+14h]
0x18005ce6c  mov     r15d, [rdx+18h]
0x18005ce70  jmp     short loc_18005CE7F
0x18005ce72  cmp     eax, 10h
0x18005ce75  jb      short loc_18005CE62
0x18005ce77  mov     rbx, [rdx+14h]
0x18005ce7b  mov     r15, [rdx+1Ch]
0x18005ce7f  test    rbx, rbx
0x18005ce82  jnz     short loc_18005CE94
0x18005ce84  test    r15, r15
0x18005ce87  jnz     short loc_18005CE94
0x18005ce89  jmp     loc_18005CDCA
0x18005ce8e  mov     rbx, r9
0x18005ce91  mov     r15, r9
0x18005ce94  mov     ecx, 38h ; '8'; uBytes
0x18005ce99  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18005ce9e  mov     [r13+8], rax
0x18005cea2  test    rax, rax
0x18005cea5  jnz     short loc_18005CEC2
0x18005cea7  lea     ebx, [rax+0Eh]
0x18005ceaa  mov     rcx, r12; pCertContext
0x18005cead  call    cs:__imp_CertFreeCertificateContext
0x18005ceb3  test    rsi, rsi
0x18005ceb6  jz      short loc_18005CEF7
0x18005ceb8  mov     rcx, rsi; void *
0x18005cebb  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18005cec0  jmp     short loc_18005CEF7
0x18005cec2  mov     [rax], r12
0x18005cec5  mov     rax, [rbp+47h+var_B0.Buffer]
0x18005cec9  mov     rdx, [r13+8]
0x18005cecd  mov     [rdx+8], rax
0x18005ced1  mov     rax, [r13+8]
0x18005ced5  mov     [rax+20h], rbx
0x18005ced9  xor     ebx, ebx
0x18005cedb  mov     rax, [r13+8]
0x18005cedf  mov     [rax+10h], r15
  ... truncated ...
```
