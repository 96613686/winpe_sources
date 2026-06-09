# SslGetCertificateByHash(uchar *,ulong,int,ushort *,void *)

- ea: `0x18003f150`
- end: `0x18003f42b`
- name: `?SslGetCertificateByHash@@YAPEBU_CERT_CONTEXT@@PEAEKHPEAGPEAX@Z`
- size: `731`
- prototype: `const struct _CERT_CONTEXT *__usercall@<rax>(unsigned __int8 *@<rcx>, unsigned int@<edx>, int@<r8d>, unsigned __int16 *@<r9>, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011c34`

## callees

- `0x180021da8`
- `0x18003f150`
- `0x18003f434`
- `0x18003f740`
- `0x180049968`
- `0x180057c8c`
- `0x180057cb4`
- `0x18005c3a0`
- `0x18005d450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f2f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f2f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f381`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003f3e3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003f3e3`
- `CRYPT32!CertOpenStore` at `0x18003f2cb`
- `CRYPT32!CertOpenStore` at `0x18003f2cb`
- `CRYPT32!CertCloseStore` at `0x18003f3cc`
- `CRYPT32!CertCloseStore` at `0x18003f3cc`
- `CRYPT32!CertFreeCertificateContext` at `0x18003f3bc`
- `CRYPT32!CertFreeCertificateContext` at `0x18003f3bc`
- `CRYPT32!CertFindCertificateInStore` at `0x18003f361`
- `CRYPT32!CertFindCertificateInStore` at `0x18003f361`

## pseudocode

```c
const struct _CERT_CONTEXT *__fastcall SslGetCertificateByHash(
        unsigned __int8 *a1,
        unsigned int a2,
        int a3,
        unsigned __int16 *a4,
        void *a5)
{
  struct _CERT_CONTEXT *v5; // rbx
  CCipherMill *v10; // rcx
  CCipherMill *v11; // rcx
  const char *v12; // r9
  DWORD v13; // edi
  unsigned int v14; // eax
  HCERTSTORE v15; // rdi
  DWORD v16; // eax
  const CERT_CONTEXT *CertificateInStore; // rax
  DWORD LastError; // eax
  struct _CERT_CONTEXT *v20; // [rsp+30h] [rbp-48h] BYREF
  __int128 pvFindPara; // [rsp+38h] [rbp-40h] BYREF
  int v22; // [rsp+90h] [rbp+18h] BYREF

  v5 = 0;
  v22 = 0;
  v20 = 0;
  pvFindPara = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)v10 + 2), 25, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, a2);
  }
  DbgDumpHexString(a1, a2);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v12 = "LOCAL_MACHINE";
      if ( !a3 )
        v12 = "CURRENT_USER";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, v12);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
    {
      WPP_SF_S(*((_QWORD *)v11 + 2), 27, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, a4);
      v11 = WPP_GLOBAL_Control;
    }
  }
  if ( a3 )
  {
    v13 = 537002496;
  }
  else
  {
    v13 = 536936960;
    if ( v11 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v11 + 2), 28, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
    v14 = SslImpersonateClient(a5, &v22);
    v11 = WPP_GLOBAL_Control;
    if ( v14 )
      goto LABEL_39;
  }
  if ( v11 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)v11 + 2), 29, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
  v15 = CertOpenStore((LPCSTR)0xA, 1u, 0, v13, a4);
  if ( v15 )
  {
    LODWORD(pvFindPara) = a2;
    *((_QWORD *)&pvFindPara + 1) = a1;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
    CertificateInStore = CertFindCertificateInStore(v15, 1u, 0, 0x10000u, &pvFindPara, 0);
    v5 = (struct _CERT_CONTEXT *)CertificateInStore;
    if ( CertificateInStore )
    {
      if ( (unsigned int)CheckForLocalStoreCertificateRenewal(
                           v15,
                           CertificateInStore,
                           0,
                           (const struct _CERT_CONTEXT **)&v20) )
      {
        CertFreeCertificateContext(v5);
        v5 = v20;
      }
    }
    else if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, LastError);
    }
    CertCloseStore(v15, 0);
    goto LABEL_38;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, v16);
LABEL_38:
    v11 = WPP_GLOBAL_Control;
  }
LABEL_39:
  if ( v22 )
  {
    RevertToSelf();
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)v11 + 2), 33, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18003f150  mov     rax, rsp
0x18003f153  mov     [rax+8], rbx
0x18003f157  mov     [rax+10h], rbp
0x18003f15b  push    rsi
0x18003f15c  push    rdi
0x18003f15d  push    r13
0x18003f15f  push    r14
0x18003f161  push    r15
0x18003f163  sub     rsp, 50h
0x18003f167  xor     ebx, ebx
0x18003f169  mov     dword ptr [rax+18h], 0
0x18003f170  xorps   xmm0, xmm0
0x18003f173  mov     [rax-48h], rbx
0x18003f177  movups  xmmword ptr [rax-40h], xmm0
0x18003f17b  mov     r14, r9
0x18003f17e  mov     edi, r8d
0x18003f181  mov     esi, edx
0x18003f183  mov     rbp, rcx
0x18003f186  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f18d  lea     r15, WPP_GLOBAL_Control
0x18003f194  lea     r13, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18003f19b  cmp     rcx, r15
0x18003f19e  jz      short loc_18003F1DB
0x18003f1a0  test    byte ptr [rcx+1Ch], 20h
0x18003f1a4  jz      short loc_18003F1BC
0x18003f1a6  mov     rcx, [rcx+10h]
0x18003f1aa  lea     edx, [rbx+18h]
0x18003f1ad  mov     r8, r13
0x18003f1b0  call    WPP_SF_
0x18003f1b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f1bc  cmp     rcx, r15
0x18003f1bf  jz      short loc_18003F1DB
0x18003f1c1  test    byte ptr [rcx+1Ch], 4
0x18003f1c5  jz      short loc_18003F1DB
0x18003f1c7  mov     rcx, [rcx+10h]
0x18003f1cb  mov     edx, 19h
0x18003f1d0  mov     r9d, esi
0x18003f1d3  mov     r8, r13
0x18003f1d6  call    WPP_SF_d
0x18003f1db  mov     edx, esi; unsigned int
0x18003f1dd  mov     rcx, rbp; unsigned __int8 *
0x18003f1e0  call    ?DbgDumpHexString@@YAXPEBEK@Z; DbgDumpHexString(uchar const *,ulong)
0x18003f1e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f1ec  cmp     rcx, r15
0x18003f1ef  jz      short loc_18003F249
0x18003f1f1  test    byte ptr [rcx+1Ch], 4
0x18003f1f5  jz      short loc_18003F223
0x18003f1f7  mov     rcx, [rcx+10h]
0x18003f1fb  lea     rax, aCurrentUser; "CURRENT_USER"
0x18003f202  test    edi, edi
0x18003f204  lea     r9, aLocalMachine; "LOCAL_MACHINE"
0x18003f20b  mov     edx, 1Ah
0x18003f210  mov     r8, r13
0x18003f213  cmovz   r9, rax
0x18003f217  call    WPP_SF_s
0x18003f21c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f223  cmp     rcx, r15
0x18003f226  jz      short loc_18003F249
0x18003f228  test    byte ptr [rcx+1Ch], 4
0x18003f22c  jz      short loc_18003F249
0x18003f22e  mov     rcx, [rcx+10h]
0x18003f232  mov     edx, 1Bh
0x18003f237  mov     r9, r14
0x18003f23a  mov     r8, r13
0x18003f23d  call    WPP_SF_S
0x18003f242  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f249  test    edi, edi
0x18003f24b  jz      short loc_18003F254
0x18003f24d  mov     edi, 20020200h
0x18003f252  jmp     short loc_18003F299
0x18003f254  mov     edi, 20010200h
0x18003f259  cmp     rcx, r15
0x18003f25c  jz      short loc_18003F275
0x18003f25e  test    byte ptr [rcx+1Ch], 4
0x18003f262  jz      short loc_18003F275
0x18003f264  mov     rcx, [rcx+10h]
0x18003f268  mov     edx, 1Ch
0x18003f26d  mov     r8, r13
0x18003f270  call    WPP_SF_
0x18003f275  mov     rcx, [rsp+78h+arg_20]; void *
0x18003f27d  lea     rdx, [rsp+78h+arg_10]; int *
0x18003f285  call    ?SslImpersonateClient@@YAKPEAXPEAH@Z; SslImpersonateClient(void *,int *)
0x18003f28a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f291  test    eax, eax
0x18003f293  jnz     loc_18003F3D9
0x18003f299  cmp     rcx, r15
0x18003f29c  jz      short loc_18003F2B5
0x18003f29e  test    byte ptr [rcx+1Ch], 4
0x18003f2a2  jz      short loc_18003F2B5
0x18003f2a4  mov     rcx, [rcx+10h]
0x18003f2a8  mov     edx, 1Dh
0x18003f2ad  mov     r8, r13
0x18003f2b0  call    WPP_SF_
0x18003f2b5  xor     r8d, r8d; hCryptProv
0x18003f2b8  mov     [rsp+78h+pvPara], r14; pvPara
0x18003f2bd  mov     r9d, edi; dwFlags
0x18003f2c0  lea     r14d, [r8+1]
0x18003f2c4  mov     edx, r14d; dwEncodingType
0x18003f2c7  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x18003f2cb  call    cs:__imp_CertOpenStore
0x18003f2d1  mov     rdi, rax
0x18003f2d4  test    rax, rax
0x18003f2d7  jnz     short loc_18003F317
0x18003f2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f2e0  cmp     rcx, r15
0x18003f2e3  jz      loc_18003F3D9
0x18003f2e9  test    [rcx+1Ch], r14b
0x18003f2ed  jz      loc_18003F3D9
0x18003f2f3  call    cs:__imp_GetLastError
0x18003f2f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f300  lea     edx, [rdi+1Eh]
0x18003f303  mov     r9d, eax
0x18003f306  mov     r8, r13
0x18003f309  mov     rcx, [rcx+10h]
0x18003f30d  call    WPP_SF_d
0x18003f312  jmp     loc_18003F3D2
0x18003f317  mov     [rsp+78h+pvFindPara], esi
0x18003f31b  mov     [rsp+78h+var_38], rbp
0x18003f320  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f327  cmp     rcx, r15
0x18003f32a  jz      short loc_18003F343
0x18003f32c  test    byte ptr [rcx+1Ch], 4
0x18003f330  jz      short loc_18003F343
0x18003f332  mov     rcx, [rcx+10h]
0x18003f336  mov     edx, 1Fh
0x18003f33b  mov     r8, r13
0x18003f33e  call    WPP_SF_
0x18003f343  lea     rax, [rsp+78h+pvFindPara]
0x18003f348  mov     [rsp+78h+pPrevCertContext], rbx; pPrevCertContext
0x18003f34d  mov     r9d, 10000h; dwFindType
0x18003f353  mov     [rsp+78h+pvPara], rax; pvFindPara
0x18003f358  xor     r8d, r8d; dwFindFlags
0x18003f35b  mov     edx, r14d; dwCertEncodingType
0x18003f35e  mov     rcx, rdi; hCertStore
0x18003f361  call    cs:__imp_CertFindCertificateInStore
0x18003f367  mov     rbx, rax
0x18003f36a  test    rax, rax
0x18003f36d  jnz     short loc_18003F3A2
0x18003f36f  mov     rax, cs:WPP_GLOBAL_Control
0x18003f376  cmp     rax, r15
0x18003f379  jz      short loc_18003F3C7
0x18003f37b  test    [rax+1Ch], r14b
0x18003f37f  jz      short loc_18003F3C7
0x18003f381  call    cs:__imp_GetLastError
0x18003f387  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f38e  lea     edx, [rbx+20h]
0x18003f391  mov     r9d, eax
0x18003f394  mov     r8, r13
0x18003f397  mov     rcx, [rcx+10h]
0x18003f39b  call    WPP_SF_d
0x18003f3a0  jmp     short loc_18003F3C7
0x18003f3a2  lea     r9, [rsp+78h+var_48]; struct _CERT_CONTEXT **
0x18003f3a7  xor     r8d, r8d; unsigned __int8
0x18003f3aa  mov     rdx, rbx; pCertContext
0x18003f3ad  mov     rcx, rdi; hCertStore
0x18003f3b0  call    ?CheckForLocalStoreCertificateRenewal@@YAHPEAXPEBU_CERT_CONTEXT@@EPEAPEBU1@@Z; CheckForLocalStoreCertificateRenewal(void *,_CERT_CONTEXT const *,uchar,_CERT_CONTEXT const * *)
0x18003f3b5  test    eax, eax
0x18003f3b7  jz      short loc_18003F3C7
0x18003f3b9  mov     rcx, rbx; pCertContext
0x18003f3bc  call    cs:__imp_CertFreeCertificateContext
0x18003f3c2  mov     rbx, [rsp+78h+var_48]
0x18003f3c7  xor     edx, edx; dwFlags
0x18003f3c9  mov     rcx, rdi; hCertStore
0x18003f3cc  call    cs:__imp_CertCloseStore
0x18003f3d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f3d9  cmp     [rsp+78h+arg_10], 0
0x18003f3e1  jz      short loc_18003F3F0
0x18003f3e3  call    cs:__imp_RevertToSelf
0x18003f3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f3f0  cmp     rcx, r15
0x18003f3f3  jz      short loc_18003F40F
0x18003f3f5  test    byte ptr [rcx+1Ch], 4
0x18003f3f9  jz      short loc_18003F40F
0x18003f3fb  mov     rcx, [rcx+10h]
0x18003f3ff  mov     edx, 21h ; '!'
0x18003f404  mov     r9, rbx
0x18003f407  mov     r8, r13
0x18003f40a  call    WPP_SF_q
0x18003f40f  lea     r11, [rsp+78h+var_28]
0x18003f414  mov     rax, rbx
0x18003f417  mov     rbx, [r11+30h]
0x18003f41b  mov     rbp, [r11+38h]
0x18003f41f  mov     rsp, r11
0x18003f422  pop     r15
0x18003f424  pop     r14
0x18003f426  pop     r13
0x18003f428  pop     rdi
0x18003f429  pop     rsi
0x18003f42a  retn
```
