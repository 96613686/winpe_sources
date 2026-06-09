# I_FindCertsInChain__lambda_6db15e1a1979103eab79e87122ee3611___lambda_e017d9558d1a18bb4771b48f362b74a8_

- ea: `0x18002dbcc`
- end: `0x18002dd7d`
- name: `I_FindCertsInChain__lambda_6db15e1a1979103eab79e87122ee3611___lambda_e017d9558d1a18bb4771b48f362b74a8___`
- size: `433`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180039f50`

## callees

- `0x18001b420`
- `0x18002121c`
- `0x18002124c`
- `0x18002dbcc`
- `0x18002dd84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc24`
- `CRYPT32!CertCompareCertificate` at `0x18002dd03`
- `CRYPT32!CertCompareCertificate` at `0x18002dd03`
- `CRYPT32!CryptMsgGetParam` at `0x18002dc1a`
- `CRYPT32!CryptMsgGetParam` at `0x18002dc1a`
- `CRYPT32!CertCreateCertificateContext` at `0x18002dca7`
- `CRYPT32!CertCreateCertificateContext` at `0x18002dca7`
- `CRYPT32!CertComparePublicKeyInfo` at `0x18002dd24`
- `CRYPT32!CertComparePublicKeyInfo` at `0x18002dd24`
- `CRYPT32!CertFreeCertificateContext` at `0x18002dd3a`
- `CRYPT32!CertFreeCertificateContext` at `0x18002dd4d`
- `CRYPT32!CertFreeCertificateContext` at `0x18002dd3a`
- `CRYPT32!CertFreeCertificateContext` at `0x18002dd4d`

## pseudocode

```c
signed int __fastcall I_FindCertsInChain__lambda_6db15e1a1979103eab79e87122ee3611___lambda_e017d9558d1a18bb4771b48f362b74a8_(
        __int64 a1,
        void *a2,
        DWORD a3,
        __int64 a4,
        __int64 cbCertEncoded)
{
  DWORD v6; // edi
  signed int result; // eax
  DWORD i; // esi
  int ParamFromMessage; // ebx
  PCCERT_CONTEXT CertificateContext; // rax
  PCCERT_CONTEXT v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // r14
  __int64 v15; // r15
  struct _CERT_INFO *pCertInfo; // rdx
  BYTE *pbCertEncoded; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 *v18; // [rsp+38h] [rbp-18h] BYREF
  PCCERT_CONTEXT pCertContext[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD pvData; // [rsp+A8h] [rbp+58h] BYREF
  int v22; // [rsp+ACh] [rbp+5Ch]

  v22 = HIDWORD(a4);
  pvData = 0;
  v6 = a3;
  LODWORD(cbCertEncoded) = 4;
  if ( CryptMsgGetParam(a2, 0xBu, 0, &pvData, (DWORD *)&cbCertEncoded) )
  {
    for ( i = 0; i < pvData; ++i )
    {
      pCertContext[0] = 0;
      pbCertEncoded = 0;
      LODWORD(cbCertEncoded) = 0;
      v18 = 0;
      ParamFromMessage = I_GetParamFromMessage(a2, 0xCu, i, &v18, (unsigned int *)&cbCertEncoded);
      if ( ParamFromMessage < 0 )
      {
        std::unique_ptr<_CRYPT_ATTRIBUTES,deleter<release::heapfree::tag>>::_Delete(&pbCertEncoded);
        return ParamFromMessage;
      }
      std::unique_ptr<unsigned char,deleter<release::heapfree::tag>>::reset(&pbCertEncoded, v18);
      CertificateContext = CertCreateCertificateContext(v6, pbCertEncoded, cbCertEncoded);
      std::unique_ptr<_CERT_CONTEXT const,deleter<release::certcontext::tag>>::reset(pCertContext, CertificateContext);
      std::unique_ptr<_CRYPT_ATTRIBUTES,deleter<release::heapfree::tag>>::_Delete(&pbCertEncoded);
      v12 = pCertContext[0];
      if ( !pCertContext[0] )
        goto LABEL_2;
      v13 = 0;
LABEL_9:
      if ( (unsigned int)v13 >= *(_DWORD *)(a1 + 12) )
      {
        CertFreeCertificateContext(v12);
        return -2146869243;
      }
      v14 = 0;
      v15 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8 * v13);
      while ( 1 )
      {
        if ( (unsigned int)v14 >= *(_DWORD *)(v15 + 12) )
        {
          v13 = (unsigned int)(v13 + 1);
          goto LABEL_9;
        }
        pCertInfo = v12->pCertInfo;
        cbCertEncoded = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 16) + 8 * v14) + 8LL);
        if ( CertCompareCertificate(a3, pCertInfo, *(PCERT_INFO *)(cbCertEncoded + 24)) )
        {
          if ( CertComparePublicKeyInfo(
                 a3,
                 &v12->pCertInfo->SubjectPublicKeyInfo,
                 (PCERT_PUBLIC_KEY_INFO)(*(_QWORD *)(cbCertEncoded + 24) + 96LL)) )
          {
            break;
          }
        }
        v14 = (unsigned int)(v14 + 1);
      }
      CertFreeCertificateContext(v12);
      v6 = a3;
    }
    return 0;
  }
  else
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18002dbcc  mov     r11, rsp
0x18002dbcf  mov     [r11+8], rbx
0x18002dbd3  mov     [r11+20h], r9
0x18002dbd7  mov     [r11+18h], r8d
0x18002dbdb  push    rbp
0x18002dbdc  push    rsi
0x18002dbdd  push    rdi
0x18002dbde  push    r12
0x18002dbe0  push    r13
0x18002dbe2  push    r14
0x18002dbe4  push    r15
0x18002dbe6  mov     rbp, rsp
0x18002dbe9  sub     rsp, 50h
0x18002dbed  mov     r12, rdx
0x18002dbf0  mov     [rbp+pvData], 0
0x18002dbf7  mov     edi, r8d
0x18002dbfa  mov     dword ptr [rbp+cbCertEncoded], 4
0x18002dc01  xor     r8d, r8d; dwIndex
0x18002dc04  lea     rax, [rbp+cbCertEncoded]
0x18002dc08  mov     r13, rcx
0x18002dc0b  mov     [r11-68h], rax
0x18002dc0f  lea     r9, [rbp+pvData]; pvData
0x18002dc13  mov     rcx, r12; hCryptMsg
0x18002dc16  lea     edx, [r8+0Bh]; dwParamType
0x18002dc1a  call    cs:__imp_CryptMsgGetParam
0x18002dc20  test    eax, eax
0x18002dc22  jnz     short loc_18002DC3F
0x18002dc24  call    cs:__imp_GetLastError
0x18002dc2a  test    eax, eax
0x18002dc2c  jle     loc_18002DD65
0x18002dc32  movzx   eax, ax
0x18002dc35  or      eax, 80070000h
0x18002dc3a  jmp     loc_18002DD65
0x18002dc3f  xor     esi, esi
0x18002dc41  cmp     esi, [rbp+pvData]
0x18002dc44  jnb     loc_18002DD63
0x18002dc4a  lea     rax, [rbp+cbCertEncoded]
0x18002dc4e  mov     [rbp+pCertContext], 0
0x18002dc56  lea     r9, [rbp+var_18]; unsigned __int8 **
0x18002dc5a  mov     [rsp+50h+var_30], rax; unsigned int *
0x18002dc5f  mov     r8d, esi; dwIndex
0x18002dc62  mov     [rbp+pbCertEncoded], 0
0x18002dc6a  mov     edx, 0Ch; dwParamType
0x18002dc6f  mov     dword ptr [rbp+cbCertEncoded], 0
0x18002dc76  mov     rcx, r12; hCryptMsg
0x18002dc79  mov     [rbp+var_18], 0
0x18002dc81  call    ?I_GetParamFromMessage@@YAJPEAXKKPEAPEAEPEAK@Z; I_GetParamFromMessage(void *,ulong,ulong,uchar * *,ulong *)
0x18002dc86  lea     rcx, [rbp+pbCertEncoded]
0x18002dc8a  mov     ebx, eax
0x18002dc8c  test    eax, eax
0x18002dc8e  js      loc_18002DD5A
0x18002dc94  mov     rdx, [rbp+var_18]
0x18002dc98  call    ?reset@?$unique_ptr@EU?$deleter@Utag@heapfree@release@@@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar,deleter<release::heapfree::tag>>::reset(uchar *)
0x18002dc9d  mov     r8d, dword ptr [rbp+cbCertEncoded]; cbCertEncoded
0x18002dca1  mov     ecx, edi; dwCertEncodingType
0x18002dca3  mov     rdx, [rbp+pbCertEncoded]; pbCertEncoded
0x18002dca7  call    cs:__imp_CertCreateCertificateContext
0x18002dcad  mov     rdx, rax
0x18002dcb0  lea     rcx, [rbp+pCertContext]
0x18002dcb4  call    ?reset@?$unique_ptr@$$CBU_CERT_CONTEXT@@U?$deleter@Utag@certcontext@release@@@@@std@@QEAAXPEBU_CERT_CONTEXT@@@Z; std::unique_ptr<_CERT_CONTEXT const,deleter<release::certcontext::tag>>::reset(_CERT_CONTEXT const *)
0x18002dcb9  lea     rcx, [rbp+pbCertEncoded]
0x18002dcbd  call    ?_Delete@?$unique_ptr@U_CRYPT_ATTRIBUTES@@U?$deleter@Utag@heapfree@release@@@@@std@@AEAAXXZ; std::unique_ptr<_CRYPT_ATTRIBUTES,deleter<release::heapfree::tag>>::_Delete(void)
0x18002dcc2  mov     rbx, [rbp+pCertContext]
0x18002dcc6  test    rbx, rbx
0x18002dcc9  jz      loc_18002DC24
0x18002dccf  xor     edi, edi
0x18002dcd1  cmp     edi, [r13+0Ch]
0x18002dcd5  jnb     short loc_18002DD4A
0x18002dcd7  mov     rax, [r13+10h]
0x18002dcdb  xor     r14d, r14d
0x18002dcde  mov     r15, [rax+rdi*8]
0x18002dce2  cmp     r14d, [r15+0Ch]
0x18002dce6  jnb     short loc_18002DD33
0x18002dce8  mov     rax, [r15+10h]
0x18002dcec  mov     rdx, [rbx+18h]; pCertId1
0x18002dcf0  mov     rcx, [rax+r14*8]
0x18002dcf4  mov     rax, [rcx+8]
0x18002dcf8  mov     ecx, [rbp+dwCertEncodingType]; dwCertEncodingType
0x18002dcfb  mov     [rbp+cbCertEncoded], rax
0x18002dcff  mov     r8, [rax+18h]; pCertId2
0x18002dd03  call    cs:__imp_CertCompareCertificate
0x18002dd09  test    eax, eax
0x18002dd0b  jz      short loc_18002DD2E
0x18002dd0d  mov     rdx, [rbx+18h]
0x18002dd11  mov     r8, [rbp+cbCertEncoded]
0x18002dd15  add     rdx, 60h ; '`'; pPublicKey1
0x18002dd19  mov     ecx, [rbp+dwCertEncodingType]; dwCertEncodingType
0x18002dd1c  mov     r8, [r8+18h]
0x18002dd20  add     r8, 60h ; '`'; pPublicKey2
0x18002dd24  call    cs:__imp_CertComparePublicKeyInfo
0x18002dd2a  test    eax, eax
0x18002dd2c  jnz     short loc_18002DD37
0x18002dd2e  inc     r14d
0x18002dd31  jmp     short loc_18002DCE2
0x18002dd33  inc     edi
0x18002dd35  jmp     short loc_18002DCD1
0x18002dd37  mov     rcx, rbx; pCertContext
0x18002dd3a  call    cs:__imp_CertFreeCertificateContext
0x18002dd40  mov     edi, [rbp+dwCertEncodingType]
0x18002dd43  inc     esi
0x18002dd45  jmp     loc_18002DC41
0x18002dd4a  mov     rcx, rbx; pCertContext
0x18002dd4d  call    cs:__imp_CertFreeCertificateContext
0x18002dd53  mov     eax, 80096005h
0x18002dd58  jmp     short loc_18002DD65
0x18002dd5a  call    ?_Delete@?$unique_ptr@U_CRYPT_ATTRIBUTES@@U?$deleter@Utag@heapfree@release@@@@@std@@AEAAXXZ; std::unique_ptr<_CRYPT_ATTRIBUTES,deleter<release::heapfree::tag>>::_Delete(void)
0x18002dd5f  mov     eax, ebx
0x18002dd61  jmp     short loc_18002DD65
0x18002dd63  xor     eax, eax
0x18002dd65  mov     rbx, [rsp+50h+arg_0]
0x18002dd6d  add     rsp, 50h
0x18002dd71  pop     r15
0x18002dd73  pop     r14
0x18002dd75  pop     r13
0x18002dd77  pop     r12
0x18002dd79  pop     rdi
0x18002dd7a  pop     rsi
0x18002dd7b  pop     rbp
0x18002dd7c  retn
```
