# AcquireDefaultClientCredential(CSsl3TlsClientContext *,int)

- ea: `0x180006c38`
- end: `0x180006f14`
- name: `?AcquireDefaultClientCredential@@YAKPEAVCSsl3TlsClientContext@@H@Z`
- size: `732`
- prototype: `unsigned int __fastcall(struct CSsl3TlsClientContext *this, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180078de4`

## callees

- `0x1800069b0`
- `0x180006c00`
- `0x180006c38`
- `0x180007934`
- `0x180014240`
- `0x180021da8`
- `0x180021e64`
- `0x180021eb0`
- `0x18003f740`
- `0x18004c5ec`
- `0x180057c8c`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089741`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006ded`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006eaf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006ded`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006eaf`
- `ntdll!NtSetInformationThread` at `0x180006ccc`
- `ntdll!NtSetInformationThread` at `0x180006ccc`
- `ntdll!RtlNtStatusToDosError` at `0x180006cdf`
- `ntdll!RtlNtStatusToDosError` at `0x180006cdf`
- `CRYPT32!CertOpenStore` at `0x180089733`
- `CRYPT32!CertOpenStore` at `0x180089733`
- `CRYPT32!CertCloseStore` at `0x1800898b8`
- `CRYPT32!CertCloseStore` at `0x1800898b8`

## pseudocode

```c
__int64 __fastcall AcquireDefaultClientCredential(struct CSsl3TlsClientContext *this, int a2)
{
  CERT_NAME_BLOB *v2; // r15
  unsigned __int8 v3; // r14
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // eax
  int v9; // esi
  signed int CredentialManagerForCert; // ebx
  unsigned __int16 *v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rax
  DWORD v15; // esi
  unsigned int v16; // ecx
  unsigned __int8 *v17; // rbx
  unsigned __int8 *v18; // rdx
  unsigned __int64 v19; // r8
  unsigned __int8 *i; // rax
  DWORD j; // r8d
  __int64 v22; // rdx
  int v23; // ecx
  HCERTSTORE v24; // r14
  bool v25; // zf
  _CERT_CHAIN_FIND_BY_ISSUER_PARA v26; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int8 v27; // [rsp+C0h] [rbp+40h] BYREF
  int v28; // [rsp+D0h] [rbp+50h] BYREF
  __int64 ThreadInformation; // [rsp+D8h] [rbp+58h] BYREF

  v2 = 0;
  v3 = 0;
  v27 = 0;
  memset(&v26, 0, sizeof(v26));
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids);
  v6 = *((_QWORD *)this + 13);
  v28 = 0;
  v7 = *(_QWORD *)(v6 + 816);
  ThreadInformation = v7;
  if ( LsaTable )
  {
    if ( v7 )
      v8 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    else
      v8 = (*(__int64 (**)(void))(LsaTable + 88))();
    v9 = 0;
    if ( v8 >= 0 )
    {
      v28 = 1;
      v9 = 1;
    }
    CredentialManagerForCert = RtlNtStatusToDosError(v8);
    if ( CredentialManagerForCert )
      goto LABEL_8;
    if ( v9 )
    {
      v13 = IsThreadLocalSystemOrNetworkService(&v27);
      if ( v13
        && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids, v13);
      }
      RevertToSelf();
      v3 = v27;
      v28 = 0;
    }
  }
  if ( !*((_DWORD *)this + 692) )
  {
    v12 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct CSsl3TlsClientContext *))(*(_QWORD *)this + 352LL))(this);
    CredentialManagerForCert = QueryCredentialManagerForCert(this, v12);
    CSsl3TlsClientContext::SetDefCredSearched(this, 1);
    if ( CredentialManagerForCert >= 0 )
    {
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids);
      goto LABEL_8;
    }
  }
  if ( a2 )
  {
    CredentialManagerForCert = 590624;
    goto LABEL_8;
  }
  v14 = *((_QWORD *)this + 327);
  v15 = 0;
  if ( v14 )
  {
    v16 = *((_DWORD *)this + 652);
    if ( v16 > 2 )
    {
      v17 = (unsigned __int8 *)(v14 + 2);
      v18 = (unsigned __int8 *)(v14 + 2);
      v19 = v14 + 2 + v16 - 2;
      for ( i = (unsigned __int8 *)(v14 + 3); (unsigned __int64)i < v19; i = v18 + 1 )
      {
        v18 += (v18[1] | ((unsigned __int64)*v18 << 8)) + 2;
        ++v15;
      }
      v2 = (CERT_NAME_BLOB *)SPExternalAlloc(16 * v15);
      if ( !v2 )
      {
        CredentialManagerForCert = -2146893056;
        goto LABEL_8;
      }
      for ( j = 0; j < v15; v17 += (unsigned int)(v23 + 2) )
      {
        v22 = j++;
        v2[v22].pbData = v17 + 2;
        v23 = v17[1] | (*v17 << 8);
        v2[v22].cbData = v23;
      }
    }
  }
  CredentialManagerForCert = SslImpersonateClient(*(void **)(*((_QWORD *)this + 13) + 816LL), &v28);
  if ( !CredentialManagerForCert )
  {
    v24 = CertOpenStore((LPCSTR)0xA, 1u, 0, v3 != 0 ? 180228 : 114692, L"MY");
    if ( !v24 )
    {
      CredentialManagerForCert = GetLastError();
      goto LABEL_8;
    }
    v25 = *((_DWORD *)this + 692) == 1;
    *(_OWORD *)&v26.dwKeySpec = 0;
    v26.pvFindArg = 0;
    *(&v26.cbSize + 1) = 0;
    v26.cIssuer = v15;
    v26.pfnFindCallback = 0;
    v26.pszUsageIdentifier = "1.3.6.1.5.5.7.3.2";
    v26.cbSize = 56;
    v26.dwKeySpec = 0;
    v26.rgIssuer = v2;
    if ( v25 )
    {
      CredentialManagerForCert = FindClientCertificate(
                                   this,
                                   v24,
                                   (const struct _CERT_CHAIN_CONTEXT **)this + 345,
                                   &v26,
                                   &v28,
                                   1,
                                   1);
      if ( CredentialManagerForCert >= 0 )
        goto LABEL_63;
      CSsl3TlsClientContext::SetDefCredSearched(this, 2);
    }
    if ( *((_DWORD *)this + 692) == 2 )
    {
      CredentialManagerForCert = FindClientCertificate(
                                   this,
                                   v24,
                                   (const struct _CERT_CHAIN_CONTEXT **)this + 345,
                                   &v26,
                                   &v28,
                                   1,
                                   0);
      if ( CredentialManagerForCert >= 0 )
        goto LABEL_63;
      CSsl3TlsClientContext::SetDefCredSearched(this, 3);
    }
    if ( *((_DWORD *)this + 692) == 3 )
    {
      CredentialManagerForCert = FindClientCertificate(
                                   this,
                                   v24,
                                   (const struct _CERT_CHAIN_CONTEXT **)this + 345,
                                   &v26,
                                   &v28,
                                   0,
                                   1);
      if ( CredentialManagerForCert >= 0 )
        goto LABEL_63;
      CSsl3TlsClientContext::SetDefCredSearched(this, 4);
    }
    if ( *((_DWORD *)this + 692) != 4 )
    {
LABEL_62:
      CredentialManagerForCert = 590624;
      goto LABEL_63;
    }
    CredentialManagerForCert = FindClientCertificate(
                                 this,
                                 v24,
                                 (const struct _CERT_CHAIN_CONTEXT **)this + 345,
                                 &v26,
                                 &v28,
                                 0,
                                 0);
    if ( CredentialManagerForCert < 0 )
    {
      CSsl3TlsClientContext::SetDefCredSearched(this, 5);
      goto LABEL_62;
    }
LABEL_63:
    CertCloseStore(v24, 0);
  }
LABEL_8:
  if ( v28 )
    RevertToSelf();
  if ( v2 )
    SPExternalFree(v2);
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids,
        (unsigned int)CredentialManagerForCert);
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
      && ((*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && CredentialManagerForCert
       || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0) )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids,
        (unsigned int)CredentialManagerForCert,
        CredentialManagerForCert);
    }
  }
  return (unsigned int)CredentialManagerForCert;
}

```

## disassembly

```asm
0x180006c38  push    rbp
0x180006c3a  push    rbx
0x180006c3b  push    rsi
0x180006c3c  push    rdi
0x180006c3d  push    r12
0x180006c3f  push    r14
0x180006c41  push    r15
0x180006c43  mov     rbp, rsp
0x180006c46  sub     rsp, 80h
0x180006c4d  xorps   xmm0, xmm0
0x180006c50  xor     eax, eax
0x180006c52  xor     r15d, r15d
0x180006c55  mov     [rbp+var_40.pvFindArg], rax
0x180006c59  xor     r14b, r14b
0x180006c5c  mov     r12d, edx
0x180006c5f  mov     [rbp+arg_0], r14b
0x180006c63  mov     rdi, rcx
0x180006c66  movups  xmmword ptr [rbp+var_40.cbSize], xmm0
0x180006c6a  movups  xmmword ptr [rbp+var_40.dwKeySpec], xmm0
0x180006c6e  movups  xmmword ptr [rbp+var_40.rgIssuer], xmm0
0x180006c72  mov     rax, cs:WPP_GLOBAL_Control
0x180006c79  lea     rsi, WPP_GLOBAL_Control
0x180006c80  cmp     rax, rsi
0x180006c83  jnz     loc_180006D51
0x180006c89  mov     rax, [rdi+68h]
0x180006c8d  mov     ebx, 1
0x180006c92  mov     [rbp+arg_10], r15d
0x180006c96  mov     rcx, [rax+330h]
0x180006c9d  mov     rax, cs:LsaTable
0x180006ca4  mov     [rbp+ThreadInformation], rcx
0x180006ca8  test    rax, rax
0x180006cab  jz      loc_180006D38
0x180006cb1  test    rcx, rcx
0x180006cb4  jz      loc_180006E00
0x180006cba  lea     r9d, [rbx+7]; ThreadInformationLength
0x180006cbe  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180006cc5  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x180006cc9  lea     edx, [rbx+4]; ThreadInformationClass
0x180006ccc  call    cs:__imp_NtSetInformationThread
0x180006cd2  xor     esi, esi
0x180006cd4  test    eax, eax
0x180006cd6  js      short loc_180006CDD
0x180006cd8  mov     [rbp+arg_10], ebx
0x180006cdb  mov     esi, ebx
0x180006cdd  mov     ecx, eax; Status
0x180006cdf  call    cs:__imp_RtlNtStatusToDosError
0x180006ce5  mov     ebx, eax
0x180006ce7  test    eax, eax
0x180006ce9  jz      short loc_180006D29
0x180006ceb  cmp     [rbp+arg_10], 0
0x180006cef  jnz     loc_180006EAF
0x180006cf5  test    r15, r15
0x180006cf8  jnz     loc_180006EBA
0x180006cfe  mov     rax, cs:WPP_GLOBAL_Control
0x180006d05  lea     rdi, WPP_GLOBAL_Control
0x180006d0c  cmp     rax, rdi
0x180006d0f  jnz     loc_180006E0E
0x180006d15  mov     eax, ebx
0x180006d17  add     rsp, 80h
0x180006d1e  pop     r15
0x180006d20  pop     r14
0x180006d22  pop     r12
0x180006d24  pop     rdi
0x180006d25  pop     rsi
0x180006d26  pop     rbx
0x180006d27  pop     rbp
0x180006d28  retn
0x180006d29  test    esi, esi
0x180006d2b  jnz     loc_180006DD9
0x180006d31  lea     rsi, WPP_GLOBAL_Control
0x180006d38  cmp     [rdi+0AD0h], r15d
0x180006d3f  jz      short loc_180006D75
0x180006d41  test    r12d, r12d
0x180006d44  jz      loc_180006E77
0x180006d4a  mov     ebx, 90320h
0x180006d4f  jmp     short loc_180006CEB
0x180006d51  test    byte ptr [rax+1Ch], 20h
0x180006d55  jz      loc_180006C89
0x180006d5b  mov     rcx, [rax+10h]
0x180006d5f  lea     r8, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids
0x180006d66  mov     edx, 14h
0x180006d6b  call    WPP_SF_
0x180006d70  jmp     loc_180006C89
0x180006d75  mov     rax, [rdi]
0x180006d78  mov     rcx, rdi
0x180006d7b  mov     rax, [rax+160h]
0x180006d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d87  mov     rdx, rax; unsigned __int16 *
0x180006d8a  mov     rcx, rdi; this
0x180006d8d  call    ?QueryCredentialManagerForCert@@YAKPEAVCSsl3TlsClientContext@@PEAG@Z; QueryCredentialManagerForCert(CSsl3TlsClientContext *,ushort *)
0x180006d92  mov     edx, 1
0x180006d97  mov     rcx, rdi
0x180006d9a  mov     ebx, eax
0x180006d9c  call    ?SetDefCredSearched@CSsl3TlsClientContext@@QEAAXW4eDefClientCred@@@Z; CSsl3TlsClientContext::SetDefCredSearched(eDefClientCred)
0x180006da1  test    ebx, ebx
0x180006da3  js      short loc_180006D41
0x180006da5  mov     rax, cs:WPP_GLOBAL_Control
0x180006dac  cmp     rax, rsi
0x180006daf  jz      loc_180006CEB
0x180006db5  test    byte ptr [rax+1Ch], 4
0x180006db9  jz      loc_180006CEB
0x180006dbf  mov     rcx, [rax+10h]
0x180006dc3  lea     r8, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids
0x180006dca  mov     edx, 16h
0x180006dcf  call    WPP_SF_
0x180006dd4  jmp     loc_180006CEB
0x180006dd9  lea     rcx, [rbp+arg_0]; unsigned __int8 *
0x180006ddd  call    ?IsThreadLocalSystemOrNetworkService@@YAKPEAE@Z; IsThreadLocalSystemOrNetworkService(uchar *)
0x180006de2  test    eax, eax
0x180006de4  jnz     short loc_180006E41
0x180006de6  lea     rsi, WPP_GLOBAL_Control
0x180006ded  call    cs:__imp_RevertToSelf
0x180006df3  mov     r14b, [rbp+arg_0]
0x180006df7  mov     [rbp+arg_10], r15d
0x180006dfb  jmp     loc_180006D38
0x180006e00  mov     rax, [rax+58h]
0x180006e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e09  jmp     loc_180006CD2
0x180006e0e  test    byte ptr [rax+1Ch], 4
0x180006e12  jnz     loc_180006EC7
0x180006e18  mov     rax, cs:WPP_GLOBAL_Control
0x180006e1f  cmp     rax, rdi
0x180006e22  jz      loc_180006D15
0x180006e28  test    byte ptr [rax+1Ch], 1
0x180006e2c  jnz     loc_180006EE4
0x180006e32  test    byte ptr [rax+1Ch], 4
0x180006e36  jz      loc_180006D15
0x180006e3c  jmp     loc_180006EEC
0x180006e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e48  lea     rsi, WPP_GLOBAL_Control
0x180006e4f  cmp     rcx, rsi
0x180006e52  jz      short loc_180006DED
0x180006e54  test    byte ptr [rcx+1Ch], 2
0x180006e58  jz      short loc_180006DED
0x180006e5a  mov     rcx, [rcx+10h]
0x180006e5e  lea     r8, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids
0x180006e65  mov     edx, 15h
0x180006e6a  mov     r9d, eax
0x180006e6d  call    WPP_SF_d
0x180006e72  jmp     loc_180006DED
0x180006e77  mov     rax, [rdi+0A38h]
0x180006e7e  xor     esi, esi
0x180006e80  test    rax, rax
0x180006e83  jz      loc_1800896EC
0x180006e89  mov     ecx, [rdi+0A30h]
0x180006e8f  cmp     ecx, 2
0x180006e92  jbe     loc_1800896EC
0x180006e98  lea     rbx, [rax+2]
0x180006e9c  lea     r8d, [rcx-2]
0x180006ea0  mov     rdx, rbx
0x180006ea3  add     r8, rbx
0x180006ea6  lea     rax, [rbx+1]
0x180006eaa  jmp     loc_180089697
0x180006eaf  call    cs:__imp_RevertToSelf
0x180006eb5  jmp     loc_180006CF5
0x180006eba  mov     rcx, r15; void *
0x180006ebd  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x180006ec2  jmp     loc_180006CFE
0x180006ec7  mov     rcx, [rax+10h]
0x180006ecb  lea     r8, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids
0x180006ed2  mov     edx, 17h
0x180006ed7  mov     r9d, ebx
0x180006eda  call    WPP_SF_d
0x180006edf  jmp     loc_180006E18
0x180006ee4  test    ebx, ebx
0x180006ee6  jz      loc_180006E32
0x180006eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ef3  lea     r8, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids
0x180006efa  mov     edx, 18h
0x180006eff  mov     dword ptr [rsp+80h+pvPara], ebx
0x180006f03  mov     r9d, ebx
0x180006f06  mov     rcx, [rcx+10h]
0x180006f0a  call    WPP_SF_dd
0x180006f0f  jmp     loc_180006D15
0x18008967c  movzx   eax, byte ptr [rdx+1]
0x180089680  movzx   ecx, byte ptr [rdx]
0x180089683  add     rdx, 2
0x180089687  shl     rcx, 8
0x18008968b  or      rcx, rax
0x18008968e  add     rdx, rcx
0x180089691  inc     esi
0x180089693  lea     rax, [rdx+1]
0x180089697  cmp     rax, r8
0x18008969a  jb      short loc_18008967C
0x18008969c  mov     ecx, esi
0x18008969e  shl     ecx, 4; uBytes
0x1800896a1  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x1800896a6  mov     r15, rax
0x1800896a9  test    rax, rax
0x1800896ac  jnz     short loc_1800896B8
0x1800896ae  mov     ebx, 80090300h
0x1800896b3  jmp     loc_180006CEB
0x1800896b8  xor     r8d, r8d
0x1800896bb  test    esi, esi
0x1800896bd  jz      short loc_1800896EC
0x1800896bf  lea     rax, [rbx+2]
0x1800896c3  mov     edx, r8d
0x1800896c6  add     rdx, rdx
0x1800896c9  inc     r8d
0x1800896cc  mov     [r15+rdx*8+8], rax
0x1800896d1  movzx   ecx, byte ptr [rbx]
0x1800896d4  movzx   eax, byte ptr [rbx+1]
0x1800896d8  shl     ecx, 8
0x1800896db  or      ecx, eax
0x1800896dd  mov     [r15+rdx*8], ecx
0x1800896e1  add     ecx, 2
0x1800896e4  add     rbx, rcx
0x1800896e7  cmp     r8d, esi
0x1800896ea  jb      short loc_1800896BF
0x1800896ec  mov     rcx, [rdi+68h]
0x1800896f0  lea     rdx, [rbp+arg_10]; int *
0x1800896f4  mov     rcx, [rcx+330h]; void *
0x1800896fb  call    ?SslImpersonateClient@@YAKPEAXPEAH@Z; SslImpersonateClient(void *,int *)
0x180089700  mov     ebx, eax
0x180089702  test    eax, eax
0x180089704  jnz     loc_180006CEB
0x18008970a  lea     rax, aMy; "MY"
0x180089711  neg     r14b
0x180089714  lea     edx, [rbx+1]; dwEncodingType
0x180089717  mov     [rsp+80h+pvPara], rax; pvPara
0x18008971c  sbb     r9d, r9d
0x18008971f  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x180089722  and     r9d, 10000h
0x180089729  xor     r8d, r8d; hCryptProv
0x18008972c  add     r9d, 1C004h; dwFlags
0x180089733  call    cs:__imp_CertOpenStore
0x180089739  mov     r14, rax
0x18008973c  test    rax, rax
0x18008973f  jnz     short loc_18008974E
0x180089741  call    cs:__imp_GetLastError
0x180089747  mov     ebx, eax
0x180089749  jmp     loc_180006CEB
0x18008974e  xor     eax, eax
0x180089750  xorps   xmm0, xmm0
0x180089753  cmp     dword ptr [rdi+0AD0h], 1
0x18008975a  movups  xmmword ptr [rbp+var_40.dwKeySpec], xmm0
0x18008975e  mov     [rbp+var_40.pvFindArg], rax
0x180089762  lea     rax, Str1; "1.3.6.1.5.5.7.3.2"
0x180089769  movups  xmmword ptr [rbp+var_40.cbSize], xmm0
0x18008976d  mov     [rbp+var_40.cIssuer], esi
0x180089770  lea     rsi, [rdi+0AC8h]
0x180089777  movups  xmmword ptr [rbp+var_40.rgIssuer], xmm0
0x18008977b  mov     [rbp+var_40.pszUsageIdentifier], rax
0x18008977f  mov     [rbp+var_40.cbSize], 38h ; '8'
0x180089786  mov     [rbp+var_40.dwKeySpec], 0
0x18008978d  mov     [rbp+var_40.rgIssuer], r15
0x180089791  jnz     short loc_1800897D5
0x180089793  mov     [rsp+80h+var_50], 1; int
0x18008979b  lea     rax, [rbp+arg_10]
0x18008979f  mov     [rsp+80h+var_58], 1; int
0x1800897a7  lea     r9, [rbp+var_40]; struct _CERT_CHAIN_FIND_BY_ISSUER_PARA *
0x1800897ab  mov     r8, rsi; struct _CERT_CHAIN_CONTEXT **
0x1800897ae  mov     [rsp+80h+pvPara], rax; int *
0x1800897b3  mov     rdx, r14; hCertStore
0x1800897b6  mov     rcx, rdi; this
0x1800897b9  call    ?FindClientCertificate@@YAKPEAVCSsl3TlsClientContext@@PEAXPEAPEBU_CERT_CHAIN_CONTEXT@@PEAU_CERT_CHAIN_FIND_BY_ISSUER_PARA@@PEAHHH@Z; FindClientCertificate(CSsl3TlsClientContext *,void *,_CERT_CHAIN_CONTEXT const * *,_CERT_CHAIN_FIND_BY_ISSUER_PARA *,int *,int,int)
0x1800897be  mov     ebx, eax
0x1800897c0  test    eax, eax
0x1800897c2  jns     loc_1800898B3
0x1800897c8  mov     edx, 2
0x1800897cd  mov     rcx, rdi
0x1800897d0  call    ?SetDefCredSearched@CSsl3TlsClientContext@@QEAAXW4eDefClientCred@@@Z; CSsl3TlsClientContext::SetDefCredSearched(eDefClientCred)
0x1800897d5  cmp     dword ptr [rdi+0AD0h], 2
0x1800897dc  jnz     short loc_180089820
0x1800897de  mov     [rsp+80h+var_50], 0; int
0x1800897e6  lea     rax, [rbp+arg_10]
0x1800897ea  mov     [rsp+80h+var_58], 1; int
0x1800897f2  lea     r9, [rbp+var_40]; struct _CERT_CHAIN_FIND_BY_ISSUER_PARA *
0x1800897f6  mov     r8, rsi; struct _CERT_CHAIN_CONTEXT **
0x1800897f9  mov     [rsp+80h+pvPara], rax; int *
0x1800897fe  mov     rdx, r14; hCertStore
0x180089801  mov     rcx, rdi; this
0x180089804  call    ?FindClientCertificate@@YAKPEAVCSsl3TlsClientContext@@PEAXPEAPEBU_CERT_CHAIN_CONTEXT@@PEAU_CERT_CHAIN_FIND_BY_ISSUER_PARA@@PEAHHH@Z; FindClientCertificate(CSsl3TlsClientContext *,void *,_CERT_CHAIN_CONTEXT const * *,_CERT_CHAIN_FIND_BY_ISSUER_PARA *,int *,int,int)
0x180089809  mov     ebx, eax
0x18008980b  test    eax, eax
0x18008980d  jns     loc_1800898B3
0x180089813  mov     edx, 3
0x180089818  mov     rcx, rdi
0x18008981b  call    ?SetDefCredSearched@CSsl3TlsClientContext@@QEAAXW4eDefClientCred@@@Z; CSsl3TlsClientContext::SetDefCredSearched(eDefClientCred)
0x180089820  cmp     dword ptr [rdi+0AD0h], 3
0x180089827  jnz     short loc_180089867
0x180089829  mov     [rsp+80h+var_50], 1; int
0x180089831  lea     rax, [rbp+arg_10]
0x180089835  mov     [rsp+80h+var_58], 0; int
0x18008983d  lea     r9, [rbp+var_40]; struct _CERT_CHAIN_FIND_BY_ISSUER_PARA *
0x180089841  mov     r8, rsi; struct _CERT_CHAIN_CONTEXT **
0x180089844  mov     [rsp+80h+pvPara], rax; int *
0x180089849  mov     rdx, r14; hCertStore
0x18008984c  mov     rcx, rdi; this
0x18008984f  call    ?FindClientCertificate@@YAKPEAVCSsl3TlsClientContext@@PEAXPEAPEBU_CERT_CHAIN_CONTEXT@@PEAU_CERT_CHAIN_FIND_BY_ISSUER_PARA@@PEAHHH@Z; FindClientCertificate(CSsl3TlsClientContext *,void *,_CERT_CHAIN_CONTEXT const * *,_CERT_CHAIN_FIND_BY_ISSUER_PARA *,int *,int,int)
0x180089854  mov     ebx, eax
0x180089856  test    eax, eax
0x180089858  jns     short loc_1800898B3
0x18008985a  mov     edx, 4
0x18008985f  mov     rcx, rdi
0x180089862  call    ?SetDefCredSearched@CSsl3TlsClientContext@@QEAAXW4eDefClientCred@@@Z; CSsl3TlsClientContext::SetDefCredSearched(eDefClientCred)
0x180089867  cmp     dword ptr [rdi+0AD0h], 4
0x18008986e  jnz     short loc_1800898AE
0x180089870  mov     [rsp+80h+var_50], 0; int
0x180089878  lea     rax, [rbp+arg_10]
  ... truncated ...
```
