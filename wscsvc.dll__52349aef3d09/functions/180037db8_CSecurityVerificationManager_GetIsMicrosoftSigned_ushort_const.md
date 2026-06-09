# CSecurityVerificationManager::GetIsMicrosoftSigned(ushort const *)

- ea: `0x180037db8`
- end: `0x180038049`
- name: `?GetIsMicrosoftSigned@CSecurityVerificationManager@@QEAAJPEBG@Z`
- size: `657`
- prototype: `__int64 __fastcall(CSecurityVerificationManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800337d0`

## callees

- `0x180008e48`
- `0x180029158`
- `0x180037db8`
- `0x180038254`
- `0x18003fbf2`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037edc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037edc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037f93`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180037f89`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180037f89`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180037f13`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180037f13`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x180037ed1`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x180037ed1`
- `WINTRUST!WinVerifyTrust` at `0x180037e9d`
- `WINTRUST!WinVerifyTrust` at `0x180037ff4`
- `WINTRUST!WinVerifyTrust` at `0x180037e9d`
- `WINTRUST!WinVerifyTrust` at `0x180037ff4`

## pseudocode

```c
__int64 __fastcall CSecurityVerificationManager::GetIsMicrosoftSigned(
        CSecurityVerificationManager *this,
        const unsigned __int16 *a2)
{
  DWORD dwError; // eax
  DWORD v4; // ebx
  CThirdPartyManager *v5; // rcx
  __int64 v6; // rdx
  CRYPT_PROVIDER_DATA *v7; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  int v9; // r8d
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+30h] [rbp-89h] BYREF
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+40h] [rbp-79h] BYREF
  _QWORD v13[2]; // [rsp+58h] [rbp-61h] BYREF
  __int128 v14; // [rsp+68h] [rbp-51h]
  _DWORD pWVTData[10]; // [rsp+80h] [rbp-39h] BYREF
  _QWORD *v16; // [rsp+A8h] [rbp-11h]
  int v17; // [rsp+B0h] [rbp-9h]
  HANDLE hStateData; // [rsp+B8h] [rbp-1h]
  int v19; // [rsp+C8h] [rbp+Fh]
  GUID pgActionID; // [rsp+E0h] [rbp+27h] BYREF

  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  pPolicyPara = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  memset_0(pWVTData, 0, 0x58u);
  pWVTData[0] = 88;
  v16 = v13;
  v14 = 0;
  pWVTData[6] = 2;
  pWVTData[8] = 1;
  v17 = 1;
  v19 = 4160;
  v13[0] = 32;
  v13[1] = a2;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, a2);
  dwError = WinVerifyTrust(0, &pgActionID, pWVTData);
  v4 = dwError;
  if ( dwError )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 12;
LABEL_24:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, dwError);
    }
  }
  else
  {
    v7 = WTHelperProvDataFromStateData(hStateData);
    if ( v7 )
    {
      ProvSignerFromChain = WTHelperGetProvSignerFromChain(v7, 0, 0, 0);
      if ( ProvSignerFromChain )
      {
        pPolicyPara.cbSize = 16;
        pPolicyPara.pvExtraPolicyPara = 0;
        memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
        pPolicyStatus.cbSize = 24;
        pPolicyPara.dwFlags = 0x10000;
        if ( CertVerifyCertificateChainPolicy(
               (LPCSTR)7,
               ProvSignerFromChain->pChainContext,
               &pPolicyPara,
               &pPolicyStatus) )
        {
          dwError = pPolicyStatus.dwError;
          if ( pPolicyStatus.dwError )
          {
            v4 = pPolicyStatus.dwError;
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v6 = 16;
              goto LABEL_24;
            }
          }
        }
        else
        {
          dwError = GetLastError();
          v4 = dwError;
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 15;
            goto LABEL_24;
          }
        }
      }
      else
      {
        dwError = GetLastError();
        v4 = dwError;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 14;
          goto LABEL_24;
        }
      }
    }
    else
    {
      dwError = GetLastError();
      v4 = dwError;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 13;
        goto LABEL_24;
      }
    }
  }
  v17 = 2;
  WinVerifyTrust(0, &pgActionID, pWVTData);
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v9, v4, (__int64)a2);
  return v4;
}

```

## disassembly

```asm
0x180037db8  mov     [rsp-8+arg_0], rbx
0x180037dbd  mov     [rsp-8+arg_10], rdi
0x180037dc2  push    rbp
0x180037dc3  push    r12
0x180037dc5  push    r14
0x180037dc7  lea     rbp, [rsp-47h]
0x180037dcc  sub     rsp, 100h
0x180037dd3  mov     rax, cs:__security_cookie
0x180037dda  xor     rax, rsp
0x180037ddd  mov     [rbp+57h+var_20], rax
0x180037de1  xor     eax, eax
0x180037de3  mov     [rbp+57h+pgActionID.Data1], 0AAC56Bh
0x180037dea  mov     rdi, rdx
0x180037ded  mov     dword ptr [rbp+57h+pgActionID.Data2], 11D0CD44h
0x180037df4  xorps   xmm0, xmm0
0x180037df7  mov     dword ptr [rbp+57h+pgActionID.Data4], 0C000C28Ch
0x180037dfe  xorps   xmm1, xmm1
0x180037e01  mov     dword ptr [rbp+57h+pgActionID.Data4+4], 0EE95C24Fh
0x180037e08  lea     ebx, [rax+58h]
0x180037e0b  mov     [rbp+57h+pPolicyStatus.pvExtraPolicyStatus], rax
0x180037e0f  mov     r8d, ebx; Size
0x180037e12  lea     rcx, [rbp+57h+pWVTData]; void *
0x180037e16  xor     edx, edx; Val
0x180037e18  movups  xmmword ptr [rsp+110h+pPolicyPara.cbSize], xmm0
0x180037e1d  movups  xmmword ptr [rbp+57h+pPolicyStatus.cbSize], xmm1
0x180037e21  call    memset_0
0x180037e26  lea     rax, [rbp+57h+var_B8]
0x180037e2a  mov     [rbp+57h+pWVTData], ebx
0x180037e2d  xorps   xmm0, xmm0
0x180037e30  mov     [rbp+57h+var_68], rax
0x180037e34  movdqu  [rbp+57h+var_A8], xmm0
0x180037e39  mov     [rbp+57h+var_78], 2
0x180037e40  mov     [rbp+57h+var_70], 1
0x180037e47  mov     [rbp+57h+var_60], 1
0x180037e4e  mov     [rbp+57h+var_48], 1040h
0x180037e55  mov     [rbp+57h+var_B8], 20h ; ' '
0x180037e5d  mov     [rbp+57h+var_B0], rdi
0x180037e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180037e68  lea     r14, WPP_GLOBAL_Control
0x180037e6f  lea     r12, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x180037e76  cmp     rcx, r14
0x180037e79  jz      short loc_180037E93
0x180037e7b  test    byte ptr [rcx+1Ch], 4
0x180037e7f  jz      short loc_180037E93
0x180037e81  mov     rcx, [rcx+10h]
0x180037e85  lea     edx, [rbx-4Dh]
0x180037e88  mov     r9, rdi
0x180037e8b  mov     r8, r12
0x180037e8e  call    WPP_SF_S
0x180037e93  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x180037e97  xor     ecx, ecx; hwnd
0x180037e99  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x180037e9d  call    cs:__imp_WinVerifyTrust
0x180037ea3  mov     ebx, eax
0x180037ea5  test    eax, eax
0x180037ea7  jz      short loc_180037ECD
0x180037ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x180037eb0  cmp     rcx, r14
0x180037eb3  jz      loc_180037FE3
0x180037eb9  test    byte ptr [rcx+1Ch], 1
0x180037ebd  jz      loc_180037FE3
0x180037ec3  mov     edx, 0Ch
0x180037ec8  jmp     loc_180037FD4
0x180037ecd  mov     rcx, [rbp+57h+hStateData]; hStateData
0x180037ed1  call    cs:__imp_WTHelperProvDataFromStateData
0x180037ed7  test    rax, rax
0x180037eda  jnz     short loc_180037F08
0x180037edc  call    cs:__imp_GetLastError
0x180037ee2  mov     ebx, eax
0x180037ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x180037eeb  cmp     rcx, r14
0x180037eee  jz      loc_180037FE3
0x180037ef4  test    byte ptr [rcx+1Ch], 1
0x180037ef8  jz      loc_180037FE3
0x180037efe  mov     edx, 0Dh
0x180037f03  jmp     loc_180037FD4
0x180037f08  xor     r9d, r9d; idxCounterSigner
0x180037f0b  xor     r8d, r8d; fCounterSigner
0x180037f0e  xor     edx, edx; idxSigner
0x180037f10  mov     rcx, rax; pProvData
0x180037f13  call    cs:__imp_WTHelperGetProvSignerFromChain
0x180037f19  test    rax, rax
0x180037f1c  jnz     short loc_180037F4A
0x180037f1e  call    cs:__imp_GetLastError
0x180037f24  mov     ebx, eax
0x180037f26  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f2d  cmp     rcx, r14
0x180037f30  jz      loc_180037FE3
0x180037f36  test    byte ptr [rcx+1Ch], 1
0x180037f3a  jz      loc_180037FE3
0x180037f40  mov     edx, 0Eh
0x180037f45  jmp     loc_180037FD4
0x180037f4a  xor     ecx, ecx
0x180037f4c  mov     [rsp+110h+pPolicyPara.cbSize], 10h
0x180037f54  mov     [rbp+57h+pPolicyStatus.pvExtraPolicyStatus], rcx
0x180037f58  lea     r9, [rbp+57h+pPolicyStatus]; pPolicyStatus
0x180037f5c  xorps   xmm0, xmm0
0x180037f5f  mov     [rsp+110h+pPolicyPara.pvExtraPolicyPara], 0
0x180037f68  movups  xmmword ptr [rbp+57h+pPolicyStatus.cbSize], xmm0
0x180037f6c  mov     [rbp+57h+pPolicyStatus.cbSize], 18h
0x180037f73  lea     r8, [rsp+110h+pPolicyPara]; pPolicyPara
0x180037f78  mov     [rsp+110h+pPolicyPara.dwFlags], 10000h
0x180037f80  mov     ecx, 7; pszPolicyOID
0x180037f85  mov     rdx, [rax+38h]; pChainContext
0x180037f89  call    cs:__imp_CertVerifyCertificateChainPolicy
0x180037f8f  test    eax, eax
0x180037f91  jnz     short loc_180037FB4
0x180037f93  call    cs:__imp_GetLastError
0x180037f99  mov     ebx, eax
0x180037f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180037fa2  cmp     rcx, r14
0x180037fa5  jz      short loc_180037FE3
0x180037fa7  test    byte ptr [rcx+1Ch], 1
0x180037fab  jz      short loc_180037FE3
0x180037fad  mov     edx, 0Fh
0x180037fb2  jmp     short loc_180037FD4
0x180037fb4  mov     eax, [rbp+57h+pPolicyStatus.dwError]
0x180037fb7  test    eax, eax
0x180037fb9  jz      short loc_180037FE3
0x180037fbb  mov     ebx, eax
0x180037fbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180037fc4  cmp     rcx, r14
0x180037fc7  jz      short loc_180037FE3
0x180037fc9  test    byte ptr [rcx+1Ch], 1
0x180037fcd  jz      short loc_180037FE3
0x180037fcf  mov     edx, 10h
0x180037fd4  mov     rcx, [rcx+10h]
0x180037fd8  mov     r9d, eax
0x180037fdb  mov     r8, r12
0x180037fde  call    WPP_SF_d
0x180037fe3  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x180037fe7  mov     [rbp+57h+var_60], 2
0x180037fee  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x180037ff2  xor     ecx, ecx; hwnd
0x180037ff4  call    cs:__imp_WinVerifyTrust
0x180037ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x180038001  cmp     rcx, r14
0x180038004  jz      short loc_180038022
0x180038006  test    byte ptr [rcx+1Ch], 4
0x18003800a  jz      short loc_180038022
0x18003800c  mov     rcx, [rcx+10h]
0x180038010  mov     edx, 11h
0x180038015  mov     r9d, ebx
0x180038018  mov     [rsp+110h+var_F0], rdi
0x18003801d  call    WPP_SF_dS
0x180038022  mov     eax, ebx
0x180038024  mov     rcx, [rbp+57h+var_20]
0x180038028  xor     rcx, rsp; StackCookie
0x18003802b  call    __security_check_cookie
0x180038030  lea     r11, [rsp+110h+var_10]
0x180038038  mov     rbx, [r11+20h]
0x18003803c  mov     rdi, [r11+30h]
0x180038040  mov     rsp, r11
0x180038043  pop     r14
0x180038045  pop     r12
0x180038047  pop     rbp
0x180038048  retn
```
