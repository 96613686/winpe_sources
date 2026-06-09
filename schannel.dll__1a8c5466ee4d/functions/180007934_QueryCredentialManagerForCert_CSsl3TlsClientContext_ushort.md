# QueryCredentialManagerForCert(CSsl3TlsClientContext *,ushort *)

- ea: `0x180007934`
- end: `0x180007b48`
- name: `?QueryCredentialManagerForCert@@YAKPEAVCSsl3TlsClientContext@@PEAG@Z`
- size: `532`
- prototype: `unsigned int __fastcall(struct CSsl3TlsClientContext *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006c38`

## callees

- `0x180007934`
- `0x180009090`
- `0x180021da8`
- `0x180021e64`
- `0x18003a5e8`
- `0x180057c8c`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089982`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007ac8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800899b0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007ac8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800899b0`
- `ntdll!NtSetInformationThread` at `0x1800079cf`
- `ntdll!NtSetInformationThread` at `0x1800079cf`
- `ntdll!RtlNtStatusToDosError` at `0x1800079d9`
- `ntdll!RtlNtStatusToDosError` at `0x1800079d9`
- `CRYPT32!CertOpenStore` at `0x180089908`
- `CRYPT32!CertOpenStore` at `0x180089908`
- `CRYPT32!CertCloseStore` at `0x1800899d9`
- `CRYPT32!CertCloseStore` at `0x1800899d9`
- `CRYPT32!CertFreeCertificateContext` at `0x1800899ce`
- `CRYPT32!CertFreeCertificateContext` at `0x1800899ce`
- `CRYPT32!CertFindCertificateInStore` at `0x18008995b`
- `CRYPT32!CertFindCertificateInStore` at `0x18008995b`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x1800898d4`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x1800898d4`
- `api-ms-win-security-credentials-l1-1-0!CredIsMarshaledCredentialW` at `0x180007a2d`
- `api-ms-win-security-credentials-l1-1-0!CredIsMarshaledCredentialW` at `0x180007a2d`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180007b0d`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180007b0d`

## pseudocode

```c
__int64 __fastcall QueryCredentialManagerForCert(struct CSsl3TlsClientContext *this, unsigned __int16 *a2)
{
  BOOL v2; // edi
  ULONG ClientLogonId; // ebx
  __int64 v6; // rcx
  __int64 v7; // rax
  NTSTATUS v8; // eax
  NTSTATUS v9; // edi
  int v10; // eax
  HCERTSTORE v12; // r14
  PCCERT_CONTEXT CertificateInStore; // rsi
  int v14; // r8d
  DWORD LastError; // eax
  PVOID Buffer; // [rsp+40h] [rbp-30h] BYREF
  struct _LUID v17; // [rsp+48h] [rbp-28h] BYREF
  __int64 ThreadInformation; // [rsp+50h] [rbp-20h] BYREF
  __int128 pvFindPara; // [rsp+58h] [rbp-18h] BYREF
  enum _CRED_MARSHAL_TYPE CredType; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+48h]

  v2 = 0;
  v21 = 0;
  Buffer = 0;
  v17 = 0;
  pvFindPara = 0;
  CredType = 0;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids);
  ClientLogonId = SslGetClientLogonId(&v17);
  if ( !ClientLogonId )
  {
    v6 = *(_QWORD *)(*((_QWORD *)this + 13) + 816LL);
    v7 = LsaTable;
    ThreadInformation = v6;
    if ( LsaTable )
    {
      if ( v6 )
        v8 = NtSetInformationThread(
               (HANDLE)0xFFFFFFFFFFFFFFFELL,
               (THREADINFOCLASS)(ClientLogonId + 5),
               &ThreadInformation,
               ClientLogonId + 8);
      else
        v8 = (*(__int64 (**)(void))(LsaTable + 88))();
      v9 = v8;
      ClientLogonId = RtlNtStatusToDosError(v8);
      v2 = v9 >= 0;
      if ( ClientLogonId )
        goto LABEL_13;
      v7 = LsaTable;
    }
    v10 = (*(__int64 (__fastcall **)(struct _LUID *, __int64, unsigned __int16 *))(v7 + 328))(&v17, 1, a2);
    ClientLogonId = v10;
    if ( v10 < 0 )
    {
      if ( v10 == -1073741275
        && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids);
      }
    }
    else if ( CredIsMarshaledCredentialW(*(LPCWSTR *)(v21 + 72))
           && CredUnmarshalCredentialW(*(LPCWSTR *)(v21 + 72), &CredType, &Buffer)
           && CredType == CertCredential )
    {
      v12 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x10004u, L"MY");
      if ( v12 )
      {
        *((_QWORD *)&pvFindPara + 1) = (char *)Buffer + 4;
        LODWORD(pvFindPara) = 20;
        CertificateInStore = CertFindCertificateInStore(v12, 1u, 0, 0x10000u, &pvFindPara, 0);
        if ( CertificateInStore )
        {
          if ( v2 )
          {
            RevertToSelf();
            v2 = 0;
          }
          ClientLogonId = AssignNewClientCredential(this, CertificateInStore, v14);
          if ( (ClientLogonId & 0x80000000) == 0 )
            ClientLogonId = 0;
          CertFreeCertificateContext(CertificateInStore);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            LastError = GetLastError();
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids,
              LastError);
          }
          ClientLogonId = -2146893042;
        }
        CertCloseStore(v12, 0);
      }
      else
      {
        GetLastError();
        ClientLogonId = -2146893042;
      }
    }
    else
    {
      ClientLogonId = -2146893043;
    }
  }
LABEL_13:
  if ( v21 )
    (*(void (**)(void))(LsaTable + 48))();
  if ( Buffer )
    CredFree(Buffer);
  if ( v2 )
    RevertToSelf();
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
    && ((*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && ClientLogonId || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0) )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids,
      ClientLogonId,
      ClientLogonId);
  }
  return ClientLogonId;
}

```

## disassembly

```asm
0x180007934  mov     [rsp-28h+arg_0], rbx
0x180007939  push    rbp
0x18000793a  push    rsi
0x18000793b  push    rdi
0x18000793c  push    r14
0x18000793e  push    r15
0x180007940  mov     rbp, rsp
0x180007943  sub     rsp, 70h
0x180007947  xor     edi, edi
0x180007949  mov     [rbp+arg_18], 0
0x180007951  xorps   xmm0, xmm0
0x180007954  mov     [rbp+Buffer], rdi
0x180007958  mov     qword ptr [rbp+var_28.LowPart], rdi
0x18000795c  mov     rsi, rdx
0x18000795f  movups  [rbp+pvFindPara], xmm0
0x180007963  mov     [rbp+CredType], edi
0x180007966  mov     r15, rcx
0x180007969  mov     rcx, cs:WPP_GLOBAL_Control
0x180007970  lea     r14, WPP_GLOBAL_Control
0x180007977  cmp     rcx, r14
0x18000797a  jz      short loc_180007986
0x18000797c  test    byte ptr [rcx+1Ch], 20h
0x180007980  jnz     loc_180007ADE
0x180007986  lea     rcx, [rbp+var_28]; struct _LUID *
0x18000798a  call    ?SslGetClientLogonId@@YAKPEAU_LUID@@@Z; SslGetClientLogonId(_LUID *)
0x18000798f  mov     ebx, eax
0x180007991  test    eax, eax
0x180007993  jnz     loc_180007A40
0x180007999  mov     rax, [r15+68h]
0x18000799d  mov     rcx, [rax+330h]
0x1800079a4  mov     rax, cs:LsaTable
0x1800079ab  mov     [rbp+ThreadInformation], rcx
0x1800079af  test    rax, rax
0x1800079b2  jz      short loc_1800079F1
0x1800079b4  test    rcx, rcx
0x1800079b7  jz      loc_180007AD0
0x1800079bd  lea     r9d, [rbx+8]; ThreadInformationLength
0x1800079c1  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800079c8  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x1800079cc  lea     edx, [rbx+5]; ThreadInformationClass
0x1800079cf  call    cs:__imp_NtSetInformationThread
0x1800079d5  mov     ecx, eax; Status
0x1800079d7  mov     edi, eax
0x1800079d9  call    cs:__imp_RtlNtStatusToDosError
0x1800079df  not     edi
0x1800079e1  mov     ebx, eax
0x1800079e3  shr     edi, 1Fh
0x1800079e6  test    eax, eax
0x1800079e8  jnz     short loc_180007A40
0x1800079ea  mov     rax, cs:LsaTable
0x1800079f1  mov     rax, [rax+148h]
0x1800079f8  lea     rcx, [rbp+arg_18]
0x1800079fc  mov     [rsp+70h+pPrevCertContext], rcx
0x180007a01  mov     r9d, 3
0x180007a07  mov     r8, rsi
0x180007a0a  mov     dword ptr [rsp+70h+pvPara], 0
0x180007a12  lea     rcx, [rbp+var_28]
0x180007a16  lea     edx, [r9-2]
0x180007a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a1f  mov     ebx, eax
0x180007a21  test    eax, eax
0x180007a23  js      short loc_180007A95
0x180007a25  mov     rcx, [rbp+arg_18]
0x180007a29  mov     rcx, [rcx+48h]; MarshaledCredential
0x180007a2d  call    cs:__imp_CredIsMarshaledCredentialW
0x180007a33  test    eax, eax
0x180007a35  jnz     loc_1800898C4
0x180007a3b  mov     ebx, 8009030Dh
0x180007a40  mov     rcx, [rbp+arg_18]
0x180007a44  test    rcx, rcx
0x180007a47  jnz     loc_180007AF8
0x180007a4d  mov     rcx, [rbp+Buffer]; Buffer
0x180007a51  test    rcx, rcx
0x180007a54  jnz     loc_180007B0D
0x180007a5a  test    edi, edi
0x180007a5c  jnz     short loc_180007AC8
0x180007a5e  mov     rax, cs:WPP_GLOBAL_Control
0x180007a65  cmp     rax, r14
0x180007a68  jnz     short loc_180007A80
0x180007a6a  mov     eax, ebx
0x180007a6c  mov     rbx, [rsp+70h+arg_0]
0x180007a74  add     rsp, 70h
0x180007a78  pop     r15
0x180007a7a  pop     r14
0x180007a7c  pop     rdi
0x180007a7d  pop     rsi
0x180007a7e  pop     rbp
0x180007a7f  retn
0x180007a80  test    byte ptr [rax+1Ch], 1
0x180007a84  jnz     loc_180007B18
0x180007a8a  test    byte ptr [rax+1Ch], 4
0x180007a8e  jz      short loc_180007A6A
0x180007a90  jmp     loc_180007B20
0x180007a95  cmp     eax, 0C0000225h
0x180007a9a  jnz     short loc_180007A40
0x180007a9c  mov     rax, cs:WPP_GLOBAL_Control
0x180007aa3  cmp     rax, r14
0x180007aa6  jz      short loc_180007A40
0x180007aa8  test    byte ptr [rax+1Ch], 2
0x180007aac  jz      short loc_180007A40
0x180007aae  mov     rcx, [rax+10h]
0x180007ab2  lea     r8, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids
0x180007ab9  mov     edx, 0Dh
0x180007abe  call    WPP_SF_
0x180007ac3  jmp     loc_180007A40
0x180007ac8  call    cs:__imp_RevertToSelf
0x180007ace  jmp     short loc_180007A5E
0x180007ad0  mov     rax, [rax+58h]
0x180007ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ad9  jmp     loc_1800079D5
0x180007ade  mov     rcx, [rcx+10h]
0x180007ae2  lea     r8, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids
0x180007ae9  mov     edx, 0Ch
0x180007aee  call    WPP_SF_
0x180007af3  jmp     loc_180007986
0x180007af8  mov     rax, cs:LsaTable
0x180007aff  mov     rax, [rax+30h]
0x180007b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b08  jmp     loc_180007A4D
0x180007b0d  call    cs:__imp_CredFree
0x180007b13  jmp     loc_180007A5A
0x180007b18  test    ebx, ebx
0x180007b1a  jz      loc_180007A8A
0x180007b20  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b27  lea     r8, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids
0x180007b2e  mov     edx, 0Fh
0x180007b33  mov     dword ptr [rsp+70h+pvPara], ebx
0x180007b37  mov     r9d, ebx
0x180007b3a  mov     rcx, [rcx+10h]
0x180007b3e  call    WPP_SF_dd
0x180007b43  jmp     loc_180007A6A
0x1800898c4  mov     rcx, [rbp+arg_18]
0x1800898c8  lea     r8, [rbp+Buffer]; Credential
0x1800898cc  lea     rdx, [rbp+CredType]; CredType
0x1800898d0  mov     rcx, [rcx+48h]; MarshaledCredential
0x1800898d4  call    cs:__imp_CredUnmarshalCredentialW
0x1800898da  test    eax, eax
0x1800898dc  jz      loc_180007A3B
0x1800898e2  cmp     [rbp+CredType], 1
0x1800898e6  jnz     loc_180007A3B
0x1800898ec  xor     r8d, r8d; hCryptProv
0x1800898ef  lea     rax, aMy; "MY"
0x1800898f6  mov     r9d, 10004h; dwFlags
0x1800898fc  mov     [rsp+70h+pvPara], rax; pvPara
0x180089901  lea     edx, [r8+1]; dwEncodingType
0x180089905  lea     ecx, [rdx+9]; lpszStoreProvider
0x180089908  call    cs:__imp_CertOpenStore
0x18008990e  mov     r14, rax
0x180089911  test    rax, rax
0x180089914  jnz     short loc_180089926
0x180089916  call    cs:__imp_GetLastError
0x18008991c  mov     ebx, 8009030Eh
0x180089921  jmp     loc_1800899DF
0x180089926  mov     rax, [rbp+Buffer]
0x18008992a  xor     r8d, r8d; dwFindFlags
0x18008992d  add     rax, 4
0x180089931  mov     [rsp+70h+pPrevCertContext], 0; pPrevCertContext
0x18008993a  mov     qword ptr [rbp+pvFindPara+8], rax
0x18008993e  mov     r9d, 10000h; dwFindType
0x180089944  lea     rax, [rbp+pvFindPara]
0x180089948  mov     dword ptr [rbp+pvFindPara], 14h
0x18008994f  lea     edx, [r8+1]; dwCertEncodingType
0x180089953  mov     [rsp+70h+pvPara], rax; pvFindPara
0x180089958  mov     rcx, r14; hCertStore
0x18008995b  call    cs:__imp_CertFindCertificateInStore
0x180089961  mov     rsi, rax
0x180089964  test    rax, rax
0x180089967  jnz     short loc_1800899AC
0x180089969  mov     rax, cs:WPP_GLOBAL_Control
0x180089970  lea     rcx, WPP_GLOBAL_Control
0x180089977  cmp     rax, rcx
0x18008997a  jz      short loc_1800899A5
0x18008997c  test    byte ptr [rax+1Ch], 1
0x180089980  jz      short loc_1800899A5
0x180089982  call    cs:__imp_GetLastError
0x180089988  mov     rcx, cs:WPP_GLOBAL_Control
0x18008998f  lea     edx, [rsi+0Eh]
0x180089992  mov     r9d, eax
0x180089995  lea     r8, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids
0x18008999c  mov     rcx, [rcx+10h]
0x1800899a0  call    WPP_SF_d
0x1800899a5  mov     ebx, 8009030Eh
0x1800899aa  jmp     short loc_1800899D4
0x1800899ac  test    edi, edi
0x1800899ae  jz      short loc_1800899B8
0x1800899b0  call    cs:__imp_RevertToSelf
0x1800899b6  xor     edi, edi
0x1800899b8  mov     rdx, rsi; struct _CERT_CONTEXT *
0x1800899bb  mov     rcx, r15; this
0x1800899be  call    ?AssignNewClientCredential@@YAKPEAVCSsl3TlsClientContext@@PEBU_CERT_CONTEXT@@H@Z; AssignNewClientCredential(CSsl3TlsClientContext *,_CERT_CONTEXT const *,int)
0x1800899c3  mov     ebx, eax
0x1800899c5  test    eax, eax
0x1800899c7  js      short loc_1800899CB
0x1800899c9  xor     ebx, ebx
0x1800899cb  mov     rcx, rsi; pCertContext
0x1800899ce  call    cs:__imp_CertFreeCertificateContext
0x1800899d4  xor     edx, edx; dwFlags
0x1800899d6  mov     rcx, r14; hCertStore
0x1800899d9  call    cs:__imp_CertCloseStore
0x1800899df  lea     r14, WPP_GLOBAL_Control
0x1800899e6  jmp     loc_180007A40
```
