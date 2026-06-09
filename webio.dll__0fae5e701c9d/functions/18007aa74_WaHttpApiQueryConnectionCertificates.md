# WaHttpApiQueryConnectionCertificates

- ea: `0x18007aa74`
- end: `0x18007abea`
- name: `WaHttpApiQueryConnectionCertificates`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18007d3ec`

## callees

- `0x180013820`
- `0x1800722f0`
- `0x18007aa74`
- `0x18007af10`
- `0x1800947e8`
- `0x1800971ec`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x18007ab99`
- `CRYPT32!CertFreeCertificateContext` at `0x18007ab99`
- `SCHANNEL!SslDeserializeCertificateStore` at `0x18007ab19`
- `SCHANNEL!SslDeserializeCertificateStore` at `0x18007ab19`

## pseudocode

```c
__int64 __fastcall WaHttpApiQueryConnectionCertificates(int a1, int a2, PCCERT_CONTEXT *a3)
{
  unsigned int VariableLengthConnectionProperty; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  __int128 v11; // [rsp+30h] [rbp-30h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-20h] BYREF
  __int128 *v13; // [rsp+48h] [rbp-18h] BYREF
  int v14; // [rsp+50h] [rbp-10h] BYREF

  v14 = 0;
  v13 = 0;
  pCertContext = 0;
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_qiq(a1, 70, (_DWORD)a3, a1, a2, (__int64)a3);
  *a3 = 0;
  VariableLengthConnectionProperty = WaHttpApiQueryVariableLengthConnectionProperty(
                                       a1,
                                       a2,
                                       0,
                                       (unsigned int)&v13,
                                       (__int64)&v14);
  if ( !VariableLengthConnectionProperty )
  {
    if ( v13 )
    {
      v11 = *v13;
      v7 = SslDeserializeCertificateStore(&v11, &pCertContext);
      if ( !v7 )
      {
        *a3 = pCertContext;
        pCertContext = 0;
        goto LABEL_13;
      }
      VariableLengthConnectionProperty = v7;
      if ( (BYTE3(xmmword_1800AD710) & 4) == 0 )
        goto LABEL_13;
      v8 = 72;
      v9 = v7;
      goto LABEL_12;
    }
    VariableLengthConnectionProperty = 1359;
  }
  if ( (BYTE3(xmmword_1800AD710) & 4) == 0 )
    goto LABEL_13;
  v8 = 71;
  v9 = VariableLengthConnectionProperty;
LABEL_12:
  WPP_SF_d(538, v8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v9);
LABEL_13:
  if ( v13 )
  {
    *(_QWORD *)&v11 = v13;
    WxFreeHeapEx(&v11);
    v13 = 0;
  }
  if ( pCertContext )
  {
    CertFreeCertificateContext(pCertContext);
    pCertContext = 0;
  }
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 74, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, VariableLengthConnectionProperty);
  return VariableLengthConnectionProperty;
}

```

## disassembly

```asm
0x18007aa74  mov     [rsp-18h+arg_18], rbx
0x18007aa79  push    rbp
0x18007aa7a  push    rsi
0x18007aa7b  push    rdi
0x18007aa7c  mov     rbp, rsp
0x18007aa7f  sub     rsp, 60h
0x18007aa83  mov     rax, cs:__security_cookie
0x18007aa8a  xor     rax, rsp
0x18007aa8d  mov     [rbp+var_8], rax
0x18007aa91  mov     rdi, r8
0x18007aa94  mov     [rbp+var_10], 0
0x18007aa9b  mov     rsi, rdx
0x18007aa9e  mov     [rbp+var_18], 0
0x18007aaa6  mov     rbx, rcx
0x18007aaa9  mov     [rbp+pCertContext], 0
0x18007aab1  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007aab8  jz      short loc_18007AAD1
0x18007aaba  mov     [rsp+60h+var_38], r8
0x18007aabf  mov     edx, 46h ; 'F'
0x18007aac4  mov     r9, rcx
0x18007aac7  mov     [rsp+60h+var_40], rsi
0x18007aacc  call    WPP_SF_qiq
0x18007aad1  lea     rax, [rbp+var_10]
0x18007aad5  mov     qword ptr [rdi], 0
0x18007aadc  lea     r9, [rbp+var_18]
0x18007aae0  mov     [rsp+60h+var_40], rax
0x18007aae5  xor     r8d, r8d
0x18007aae8  mov     rdx, rsi
0x18007aaeb  mov     rcx, rbx
0x18007aaee  call    WaHttpApiQueryVariableLengthConnectionProperty
0x18007aaf3  lea     rsi, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007aafa  mov     ebx, eax
0x18007aafc  test    eax, eax
0x18007aafe  jnz     short loc_18007AB54
0x18007ab00  mov     rcx, [rbp+var_18]
0x18007ab04  test    rcx, rcx
0x18007ab07  jz      short loc_18007AB4F
0x18007ab09  movups  xmm0, xmmword ptr [rcx]
0x18007ab0c  lea     rdx, [rbp+pCertContext]
0x18007ab10  lea     rcx, [rbp+var_30]
0x18007ab14  movdqu  [rbp+var_30], xmm0
0x18007ab19  call    cs:__imp_SslDeserializeCertificateStore
0x18007ab20  nop     dword ptr [rax+rax+00h]
0x18007ab25  test    eax, eax
0x18007ab27  jz      short loc_18007AB3E
0x18007ab29  mov     ebx, eax
0x18007ab2b  test    byte ptr cs:xmmword_1800AD710+3, 4
0x18007ab32  jz      short loc_18007AB72
0x18007ab34  mov     edx, 48h ; 'H'
0x18007ab39  mov     r9d, eax
0x18007ab3c  jmp     short loc_18007AB65
0x18007ab3e  mov     rax, [rbp+pCertContext]
0x18007ab42  mov     [rdi], rax
0x18007ab45  mov     [rbp+pCertContext], 0
0x18007ab4d  jmp     short loc_18007AB72
0x18007ab4f  mov     ebx, 54Fh
0x18007ab54  test    byte ptr cs:xmmword_1800AD710+3, 4
0x18007ab5b  jz      short loc_18007AB72
0x18007ab5d  mov     edx, 47h ; 'G'
0x18007ab62  mov     r9d, ebx
0x18007ab65  mov     r8, rsi
0x18007ab68  mov     ecx, 21Ah
0x18007ab6d  call    WPP_SF_d
0x18007ab72  mov     rcx, [rbp+var_18]
0x18007ab76  test    rcx, rcx
0x18007ab79  jz      short loc_18007AB90
0x18007ab7b  mov     qword ptr [rbp+var_30], rcx
0x18007ab7f  lea     rcx, [rbp+var_30]
0x18007ab83  call    WxFreeHeapEx
0x18007ab88  mov     [rbp+var_18], 0
0x18007ab90  mov     rcx, [rbp+pCertContext]; pCertContext
0x18007ab94  test    rcx, rcx
0x18007ab97  jz      short loc_18007ABAD
0x18007ab99  call    cs:__imp_CertFreeCertificateContext
0x18007aba0  nop     dword ptr [rax+rax+00h]
0x18007aba5  mov     [rbp+pCertContext], 0
0x18007abad  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007abb4  jz      short loc_18007ABCB
0x18007abb6  mov     edx, 4Ah ; 'J'
0x18007abbb  mov     ecx, 41Ah
0x18007abc0  mov     r9d, ebx
0x18007abc3  mov     r8, rsi
0x18007abc6  call    WPP_SF_d
0x18007abcb  mov     eax, ebx
0x18007abcd  mov     rcx, [rbp+var_8]
0x18007abd1  xor     rcx, rsp; StackCookie
0x18007abd4  call    __security_check_cookie
0x18007abd9  mov     rbx, [rsp+60h+arg_18]
0x18007abe1  add     rsp, 60h
0x18007abe5  pop     rdi
0x18007abe6  pop     rsi
0x18007abe7  pop     rbp
0x18007abe8  retn
```
