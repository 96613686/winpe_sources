# SdpGetCertificate(ushort const *,_CERT_CONTEXT const * *,int *,int *)

- ea: `0x180006ca0`
- end: `0x180006ff9`
- name: `?SdpGetCertificate@@YAJPEBGPEAPEBU_CERT_CONTEXT@@PEAH2@Z`
- size: `857`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const struct _CERT_CONTEXT **, int *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180011888`
- `0x180011ba4`

## callees

- `0x180006ca0`
- `0x180007528`
- `0x180026fa0`
- `0x180029882`
- `0x1800298c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006f10`
- `KERNEL32!GetLastError` at `0x180006f2d`
- `KERNEL32!GetLastError` at `0x180006f4a`
- `KERNEL32!GetLastError` at `0x180006f67`
- `KERNEL32!GetLastError` at `0x180006f10`
- `KERNEL32!GetLastError` at `0x180006f2d`
- `KERNEL32!GetLastError` at `0x180006f4a`
- `KERNEL32!GetLastError` at `0x180006f67`
- `KERNEL32!CreateFileW` at `0x180006d79`
- `KERNEL32!CreateFileW` at `0x180006d79`
- `KERNEL32!CloseHandle` at `0x180006fc3`
- `KERNEL32!CloseHandle` at `0x180006fc3`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180006e25`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180006e25`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x180006e41`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x180006e41`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x180006e06`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x180006e06`
- `WINTRUST!WinVerifyTrust` at `0x180006de6`
- `WINTRUST!WinVerifyTrust` at `0x180006fb0`
- `WINTRUST!WinVerifyTrust` at `0x180006de6`
- `WINTRUST!WinVerifyTrust` at `0x180006fb0`
- `CRYPT32!CertFreeCertificateContext` at `0x180006fd1`
- `CRYPT32!CertFreeCertificateContext` at `0x180006fd1`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180006e72`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180006e72`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180006ee4`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180006ee4`

## pseudocode

```c
__int64 __fastcall SdpGetCertificate(LPCWSTR lpFileName, const struct _CERT_CONTEXT **a2, int *a3, int *a4)
{
  char *v6; // r15
  const CERT_CONTEXT *v7; // rsi
  unsigned int v9; // r8d
  int v10; // r9d
  int v11; // ebx
  int v12; // edi
  char *FileW; // rax
  int v14; // eax
  CRYPT_PROVIDER_DATA *v15; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_SGNR *v17; // r14
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  const CERT_CONTEXT *pCert; // rcx
  const CERT_CONTEXT *v20; // rax
  int IsWindows; // eax
  int *v22; // r12
  signed int v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  signed int LastError; // eax
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  int *v29; // [rsp+48h] [rbp-B8h]
  __int128 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v31; // [rsp+60h] [rbp-A0h]
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+70h] [rbp-90h] BYREF
  int pWVTData; // [rsp+90h] [rbp-70h] BYREF
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+B0h] [rbp-50h]
  __int128 *v38; // [rsp+B8h] [rbp-48h]
  int v39; // [rsp+C0h] [rbp-40h]
  HANDLE hStateData; // [rsp+C8h] [rbp-38h]
  __int64 v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+F0h] [rbp-10h] BYREF
  GUID pgActionID; // [rsp+100h] [rbp+0h] BYREF

  v29 = a3;
  pgActionID.Data1 = 11191659;
  v6 = 0;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  v7 = 0;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  v28 = 0;
  memset_0(&pWVTData, 0, 0x58u);
  v30 = 0;
  v31 = 0;
  pPolicyPara = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  if ( !lpFileName )
  {
    v9 = 773;
LABEL_3:
    v10 = -2147024809;
    v11 = -2147024809;
LABEL_41:
    SdpDebugTrace(1u, L"SdpGetCertificate", v9, v10);
    goto LABEL_42;
  }
  if ( !a2 )
  {
    v9 = 774;
    goto LABEL_3;
  }
  v12 = 1;
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
  v6 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v9 = 787;
    goto LABEL_37;
  }
  v31 = (unsigned __int64)FileW;
  LODWORD(v30) = 32;
  v38 = &v30;
  *((_QWORD *)&v30 + 1) = lpFileName;
  pWVTData = 88;
  v34 = 0;
  v35 = 0;
  v36 = 2;
  v37 = 1;
  v39 = 1;
  hStateData = 0;
  v41 = 0;
  v42 = 4224;
  v11 = WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, &pWVTData);
  if ( v11 )
  {
    v14 = -2143551225;
    v9 = 818;
LABEL_38:
    if ( v11 >= 0 )
      v11 = v14;
    v10 = v11;
    goto LABEL_41;
  }
  v15 = WTHelperProvDataFromStateData(hStateData);
  if ( (unsigned __int64)&v15[-1].dwUIStateFlags + 3 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v25 = GetLastError();
    v11 = v25;
    if ( v25 > 0 )
      v11 = (unsigned __int16)v25 | 0x80070000;
    v9 = 822;
    goto LABEL_37;
  }
  ProvSignerFromChain = WTHelperGetProvSignerFromChain(v15, 0, 0, 0);
  v17 = ProvSignerFromChain;
  if ( (unsigned __int64)&ProvSignerFromChain[-1].pChainContext + 7 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v24 = GetLastError();
    v11 = v24;
    if ( v24 > 0 )
      v11 = (unsigned __int16)v24 | 0x80070000;
    v9 = 825;
    goto LABEL_37;
  }
  ProvCertFromChain = WTHelperGetProvCertFromChain(ProvSignerFromChain, 0);
  if ( (unsigned __int64)&ProvCertFromChain[-1].pChainElement + 7 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v23 = GetLastError();
    v11 = v23;
    if ( v23 > 0 )
      v11 = (unsigned __int16)v23 | 0x80070000;
    v9 = 828;
LABEL_37:
    v14 = -2147467259;
    goto LABEL_38;
  }
  pCert = ProvCertFromChain->pCert;
  if ( !pCert )
  {
    v10 = -2147467261;
    v9 = 831;
    v11 = -2147467261;
    goto LABEL_41;
  }
  v20 = CertDuplicateCertificateContext(pCert);
  v7 = v20;
  if ( !v20 )
  {
    v10 = -2147467261;
    v9 = 834;
    v11 = -2147467261;
    goto LABEL_41;
  }
  IsWindows = SdpIsWindows(v20, &v28);
  v11 = IsWindows;
  if ( IsWindows < 0 )
  {
    v10 = IsWindows;
    v9 = 837;
    goto LABEL_41;
  }
  *a2 = v7;
  v7 = 0;
  v22 = v29;
  if ( v29 )
  {
    pPolicyPara.cbSize = 16;
    pPolicyStatus.cbSize = 24;
    if ( !CertVerifyCertificateChainPolicy((LPCSTR)7, v17->pChainContext, &pPolicyPara, &pPolicyStatus)
      || pPolicyStatus.dwError )
    {
      v12 = 0;
    }
    *v22 = v12;
  }
  if ( a4 )
    *a4 = v28;
LABEL_42:
  v39 = 2;
  WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, &pWVTData);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  if ( v7 )
    CertFreeCertificateContext(v7);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006ca0  push    rbp
0x180006ca2  push    rbx
0x180006ca3  push    rsi
0x180006ca4  push    rdi
0x180006ca5  push    r12
0x180006ca7  push    r13
0x180006ca9  push    r14
0x180006cab  push    r15
0x180006cad  lea     rbp, [rsp-28h]
0x180006cb2  sub     rsp, 128h
0x180006cb9  mov     rax, cs:__security_cookie
0x180006cc0  xor     rax, rsp
0x180006cc3  mov     [rbp+60h+var_50], rax
0x180006cc7  mov     [rsp+160h+var_118], r8
0x180006ccc  mov     r12, rdx
0x180006ccf  mov     rbx, rcx
0x180006cd2  mov     [rbp+60h+pgActionID.Data1], 0AAC56Bh
0x180006cd9  xor     r15d, r15d
0x180006cdc  mov     dword ptr [rbp+60h+pgActionID.Data2], 11D0CD44h
0x180006ce3  xor     esi, esi
0x180006ce5  mov     dword ptr [rbp+60h+pgActionID.Data4], 0C000C28Ch
0x180006cec  xor     edx, edx; Val
0x180006cee  mov     dword ptr [rbp+60h+pgActionID.Data4+4], 0EE95C24Fh
0x180006cf5  lea     rcx, [rbp+60h+pWVTData]; void *
0x180006cf9  mov     [rsp+160h+var_120], esi
0x180006cfd  lea     r14d, [r15+58h]
0x180006d01  mov     r13, r9
0x180006d04  mov     r8d, r14d; Size
0x180006d07  call    memset_0
0x180006d0c  xorps   xmm0, xmm0
0x180006d0f  xor     eax, eax
0x180006d11  mov     [rbp+60h+pPolicyStatus.pvExtraPolicyStatus], rax
0x180006d15  xorps   xmm1, xmm1
0x180006d18  movups  [rsp+160h+var_110], xmm0
0x180006d1d  movups  [rsp+160h+var_100], xmm0
0x180006d22  movups  xmmword ptr [rbp+60h+pPolicyPara.cbSize], xmm0
0x180006d26  movups  xmmword ptr [rsp+160h+pPolicyStatus.cbSize], xmm1
0x180006d2b  test    rbx, rbx
0x180006d2e  jnz     short loc_180006D49
0x180006d30  mov     r8d, 305h
0x180006d36  mov     r9d, 80070057h
0x180006d3c  mov     ecx, 1
0x180006d41  mov     ebx, r9d
0x180006d44  jmp     loc_180006F91
0x180006d49  test    r12, r12
0x180006d4c  jnz     short loc_180006D56
0x180006d4e  mov     r8d, 306h
0x180006d54  jmp     short loc_180006D36
0x180006d56  mov     [rsp+160h+hTemplateFile], rax; hTemplateFile
0x180006d5b  xor     r9d, r9d; lpSecurityAttributes
0x180006d5e  mov     [rsp+160h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180006d62  mov     edx, 80000000h; dwDesiredAccess
0x180006d67  mov     rcx, rbx; lpFileName
0x180006d6a  mov     [rsp+160h+dwCreationDisposition], 3; dwCreationDisposition
0x180006d72  lea     edi, [r9+1]
0x180006d76  mov     r8d, edi; dwShareMode
0x180006d79  call    cs:__imp_CreateFileW
0x180006d7f  mov     r15, rax
0x180006d82  lea     rcx, [rax-1]
0x180006d86  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180006d8a  ja      loc_180006F67
0x180006d90  mov     qword ptr [rsp+160h+var_100], rax
0x180006d95  lea     r8, [rbp+60h+pWVTData]; pWVTData
0x180006d99  lea     rax, [rsp+160h+var_110]
0x180006d9e  mov     dword ptr [rsp+160h+var_110], 20h ; ' '
0x180006da6  lea     rdx, [rbp+60h+pgActionID]; pgActionID
0x180006daa  mov     [rbp+60h+var_A8], rax
0x180006dae  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x180006db2  mov     qword ptr [rsp+160h+var_110+8], rbx
0x180006db7  mov     qword ptr [rsp+160h+var_100+8], rsi
0x180006dbc  mov     [rbp+60h+pWVTData], r14d
0x180006dc0  mov     [rbp+60h+var_C8], rsi
0x180006dc4  mov     [rbp+60h+var_C0], rsi
0x180006dc8  mov     [rbp+60h+var_B8], 2
0x180006dd0  mov     [rbp+60h+var_B0], edi
0x180006dd3  mov     [rbp+60h+var_A0], edi
0x180006dd6  mov     [rbp+60h+hStateData], rsi
0x180006dda  mov     [rbp+60h+var_90], rsi
0x180006dde  mov     [rbp+60h+var_88], 1080h
0x180006de6  call    cs:__imp_WinVerifyTrust
0x180006dec  mov     ebx, eax
0x180006dee  test    eax, eax
0x180006df0  jz      short loc_180006E02
0x180006df2  mov     eax, 803C0107h
0x180006df7  mov     r8d, 332h
0x180006dfd  jmp     loc_180006F87
0x180006e02  mov     rcx, [rbp+60h+hStateData]; hStateData
0x180006e06  call    cs:__imp_WTHelperProvDataFromStateData
0x180006e0c  lea     rcx, [rax-1]
0x180006e10  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180006e14  ja      loc_180006F4A
0x180006e1a  xor     r9d, r9d; idxCounterSigner
0x180006e1d  xor     r8d, r8d; fCounterSigner
0x180006e20  xor     edx, edx; idxSigner
0x180006e22  mov     rcx, rax; pProvData
0x180006e25  call    cs:__imp_WTHelperGetProvSignerFromChain
0x180006e2b  mov     r14, rax
0x180006e2e  lea     rcx, [rax-1]
0x180006e32  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180006e36  ja      loc_180006F2D
0x180006e3c  xor     edx, edx; idxCert
0x180006e3e  mov     rcx, rax; pSgnr
0x180006e41  call    cs:__imp_WTHelperGetProvCertFromChain
0x180006e47  lea     rcx, [rax-1]
0x180006e4b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180006e4f  ja      loc_180006F10
0x180006e55  mov     rcx, [rax+8]; pCertContext
0x180006e59  test    rcx, rcx
0x180006e5c  jnz     short loc_180006E72
0x180006e5e  mov     r9d, 80004003h
0x180006e64  mov     r8d, 33Fh
0x180006e6a  mov     ebx, r9d
0x180006e6d  jmp     loc_180006F8F
0x180006e72  call    cs:__imp_CertDuplicateCertificateContext
0x180006e78  mov     rsi, rax
0x180006e7b  test    rax, rax
0x180006e7e  jnz     short loc_180006E94
0x180006e80  mov     r9d, 80004003h
0x180006e86  mov     r8d, 342h
0x180006e8c  mov     ebx, r9d
0x180006e8f  jmp     loc_180006F8F
0x180006e94  lea     rdx, [rsp+160h+var_120]; int *
0x180006e99  mov     rcx, rsi; pCertContext
0x180006e9c  call    ?SdpIsWindows@@YAJPEBU_CERT_CONTEXT@@PEAH@Z; SdpIsWindows(_CERT_CONTEXT const *,int *)
0x180006ea1  mov     ebx, eax
0x180006ea3  test    eax, eax
0x180006ea5  jns     short loc_180006EB5
0x180006ea7  mov     r9d, eax
0x180006eaa  mov     r8d, 345h
0x180006eb0  jmp     loc_180006F8F
0x180006eb5  mov     [r12], rsi
0x180006eb9  xor     esi, esi
0x180006ebb  mov     r12, [rsp+160h+var_118]
0x180006ec0  test    r12, r12
0x180006ec3  jz      short loc_180006EFA
0x180006ec5  mov     [rbp+60h+pPolicyPara.cbSize], 10h
0x180006ecc  lea     r9, [rsp+160h+pPolicyStatus]; pPolicyStatus
0x180006ed1  mov     [rsp+160h+pPolicyStatus.cbSize], 18h
0x180006ed9  lea     r8, [rbp+60h+pPolicyPara]; pPolicyPara
0x180006edd  mov     rdx, [r14+38h]; pChainContext
0x180006ee1  lea     ecx, [rsi+7]; pszPolicyOID
0x180006ee4  call    cs:__imp_CertVerifyCertificateChainPolicy
0x180006eea  test    eax, eax
0x180006eec  jz      short loc_180006EF4
0x180006eee  cmp     [rsp+160h+pPolicyStatus.dwError], esi
0x180006ef2  jz      short loc_180006EF6
0x180006ef4  xor     edi, edi
0x180006ef6  mov     [r12], edi
0x180006efa  test    r13, r13
0x180006efd  jz      loc_180006F9D
0x180006f03  mov     eax, [rsp+160h+var_120]
0x180006f07  mov     [r13+0], eax
0x180006f0b  jmp     loc_180006F9D
0x180006f10  call    cs:__imp_GetLastError
0x180006f16  mov     ebx, eax
0x180006f18  test    eax, eax
0x180006f1a  jle     short loc_180006F25
0x180006f1c  movzx   ebx, ax
0x180006f1f  or      ebx, 80070000h
0x180006f25  mov     r8d, 33Ch
0x180006f2b  jmp     short loc_180006F82
0x180006f2d  call    cs:__imp_GetLastError
0x180006f33  mov     ebx, eax
0x180006f35  test    eax, eax
0x180006f37  jle     short loc_180006F42
0x180006f39  movzx   ebx, ax
0x180006f3c  or      ebx, 80070000h
0x180006f42  mov     r8d, 339h
0x180006f48  jmp     short loc_180006F82
0x180006f4a  call    cs:__imp_GetLastError
0x180006f50  mov     ebx, eax
0x180006f52  test    eax, eax
0x180006f54  jle     short loc_180006F5F
0x180006f56  movzx   ebx, ax
0x180006f59  or      ebx, 80070000h
0x180006f5f  mov     r8d, 336h
0x180006f65  jmp     short loc_180006F82
0x180006f67  call    cs:__imp_GetLastError
0x180006f6d  mov     ebx, eax
0x180006f6f  test    eax, eax
0x180006f71  jle     short loc_180006F7C
0x180006f73  movzx   ebx, ax
0x180006f76  or      ebx, 80070000h
0x180006f7c  mov     r8d, 313h; int
0x180006f82  mov     eax, 80004005h
0x180006f87  test    ebx, ebx
0x180006f89  cmovns  ebx, eax
0x180006f8c  mov     r9d, ebx; int
0x180006f8f  mov     ecx, edi; Level
0x180006f91  lea     rdx, aSdpgetcertific; "SdpGetCertificate"
0x180006f98  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006f9d  lea     r8, [rbp+60h+pWVTData]; pWVTData
0x180006fa1  mov     [rbp+60h+var_A0], 2
0x180006fa8  lea     rdx, [rbp+60h+pgActionID]; pgActionID
0x180006fac  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x180006fb0  call    cs:__imp_WinVerifyTrust
0x180006fb6  lea     rax, [r15-1]
0x180006fba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006fbe  ja      short loc_180006FC9
0x180006fc0  mov     rcx, r15; hObject
0x180006fc3  call    cs:__imp_CloseHandle
0x180006fc9  test    rsi, rsi
0x180006fcc  jz      short loc_180006FD7
0x180006fce  mov     rcx, rsi; pCertContext
0x180006fd1  call    cs:__imp_CertFreeCertificateContext
0x180006fd7  mov     eax, ebx
0x180006fd9  mov     rcx, [rbp+60h+var_50]
0x180006fdd  xor     rcx, rsp; StackCookie
0x180006fe0  call    __security_check_cookie
0x180006fe5  add     rsp, 128h
0x180006fec  pop     r15
0x180006fee  pop     r14
0x180006ff0  pop     r13
0x180006ff2  pop     r12
0x180006ff4  pop     rdi
0x180006ff5  pop     rsi
0x180006ff6  pop     rbx
0x180006ff7  pop     rbp
0x180006ff8  retn
```
