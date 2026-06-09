# SslDeserializeCertificateStore

- ea: `0x18003f9e0`
- end: `0x18003fba2`
- name: `SslDeserializeCertificateStore`
- size: `450`
- prototype: `__int64 __fastcall(_QWORD *pvPara, const CERT_CONTEXT **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18006f530`
- `0x18006f634`
- `0x18006f984`

## callees

- `0x180021da8`
- `0x18003f9e0`
- `0x180057c8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003faa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003faa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb3b`
- `CRYPT32!CertOpenStore` at `0x18003fa1b`
- `CRYPT32!CertOpenStore` at `0x18003fa1b`
- `CRYPT32!CertCloseStore` at `0x18003fa89`
- `CRYPT32!CertCloseStore` at `0x18003fa89`
- `CRYPT32!CertFreeCertificateContext` at `0x18008fb29`
- `CRYPT32!CertFreeCertificateContext` at `0x18008fb29`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18003fa36`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18003fa36`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18003fa6a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18003fa6a`

## pseudocode

```c
__int64 __fastcall SslDeserializeCertificateStore(_QWORD *pvPara, const CERT_CONTEXT **a2)
{
  HCERTSTORE v3; // rdi
  const CERT_CONTEXT *v4; // rsi
  const CERT_CONTEXT *v5; // rax
  unsigned int v6; // ebp
  DWORD v8; // eax
  DWORD LastError; // eax
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF

  if ( !a2 )
    return 2148074333LL;
  if ( !pvPara[1] )
    return 2148074254LL;
  v3 = CertOpenStore((LPCSTR)6, 1u, 0, 4u, pvPara);
  if ( v3 )
  {
    v4 = 0;
    while ( 1 )
    {
      v5 = CertEnumCertificatesInStore(v3, v4);
      v4 = v5;
      if ( !v5 )
        break;
      pcbData = 4;
      pvData = 0;
      if ( !CertGetCertificateContextProperty(v5, 0xE697u, &pvData, &pcbData) )
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_39e7268a77b0313df132bc71a3d61242_Traceguids, LastError);
        }
        CertFreeCertificateContext(v4);
        v6 = -2146892963;
        goto LABEL_9;
      }
      if ( !pvData )
      {
        v6 = 0;
        *a2 = v4;
        goto LABEL_9;
      }
    }
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_39e7268a77b0313df132bc71a3d61242_Traceguids);
    v6 = -2146893052;
LABEL_9:
    CertCloseStore(v3, 0);
    return v6;
  }
  else
  {
    v8 = GetLastError();
    if ( v8 == 14 || v8 == 8 )
    {
      return 2148074240LL;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_39e7268a77b0313df132bc71a3d61242_Traceguids, v8);
      return 2148074248LL;
    }
  }
}

```

## disassembly

```asm
0x18003f9e0  push    rbx
0x18003f9e2  push    rbp
0x18003f9e3  sub     rsp, 38h
0x18003f9e7  mov     rbx, rdx
0x18003f9ea  test    rdx, rdx
0x18003f9ed  jz      loc_18003FACA
0x18003f9f3  cmp     qword ptr [rcx+8], 0
0x18003f9f8  jz      loc_18003FABE
0x18003f9fe  mov     [rsp+48h+pvPara], rcx; pvPara
0x18003fa03  mov     r9d, 4; dwFlags
0x18003fa09  mov     ecx, 6; lpszStoreProvider
0x18003fa0e  mov     [rsp+48h+var_18], rdi
0x18003fa13  xor     r8d, r8d; hCryptProv
0x18003fa16  mov     edx, 1; dwEncodingType
0x18003fa1b  call    cs:__imp_CertOpenStore
0x18003fa21  mov     rdi, rax
0x18003fa24  test    rax, rax
0x18003fa27  jz      short loc_18003FAA2
0x18003fa29  mov     [rsp+48h+arg_0], rsi
0x18003fa2e  xor     esi, esi
0x18003fa30  mov     rdx, rsi; pPrevCertContext
0x18003fa33  mov     rcx, rdi; hCertStore
0x18003fa36  call    cs:__imp_CertEnumCertificatesInStore
0x18003fa3c  mov     rsi, rax
0x18003fa3f  test    rax, rax
0x18003fa42  jz      loc_18003FB66
0x18003fa48  lea     r9, [rsp+48h+pcbData]; pcbData
0x18003fa4d  mov     [rsp+48h+pcbData], 4
0x18003fa55  lea     r8, [rsp+48h+pvData]; pvData
0x18003fa5a  mov     [rsp+48h+pvData], 0
0x18003fa62  mov     edx, 0E697h; dwPropId
0x18003fa67  mov     rcx, rax; pCertContext
0x18003fa6a  call    cs:__imp_CertGetCertificateContextProperty
0x18003fa70  test    eax, eax
0x18003fa72  jz      loc_18003FB1A
0x18003fa78  cmp     [rsp+48h+pvData], 0
0x18003fa7d  jnz     short loc_18003FA30
0x18003fa7f  xor     ebp, ebp
0x18003fa81  mov     [rbx], rsi
0x18003fa84  xor     edx, edx; dwFlags
0x18003fa86  mov     rcx, rdi; hCertStore
0x18003fa89  call    cs:__imp_CertCloseStore
0x18003fa8f  mov     rsi, [rsp+48h+arg_0]
0x18003fa94  mov     eax, ebp
0x18003fa96  mov     rdi, [rsp+48h+var_18]
0x18003fa9b  add     rsp, 38h
0x18003fa9f  pop     rbp
0x18003faa0  pop     rbx
0x18003faa1  retn
0x18003faa2  call    cs:__imp_GetLastError
0x18003faa8  cmp     eax, 0Eh
0x18003faab  jnz     short loc_18003FAD6
0x18003faad  mov     rdi, [rsp+48h+var_18]
0x18003fab2  mov     eax, 80090300h
0x18003fab7  add     rsp, 38h
0x18003fabb  pop     rbp
0x18003fabc  pop     rbx
0x18003fabd  retn
0x18003fabe  mov     eax, 8009030Eh
0x18003fac3  add     rsp, 38h
0x18003fac7  pop     rbp
0x18003fac8  pop     rbx
0x18003fac9  retn
0x18003faca  mov     eax, 8009035Dh
0x18003facf  add     rsp, 38h
0x18003fad3  pop     rbp
0x18003fad4  pop     rbx
0x18003fad5  retn
0x18003fad6  cmp     eax, 8
0x18003fad9  jz      short loc_18003FAAD
0x18003fadb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fae2  lea     rdx, WPP_GLOBAL_Control
0x18003fae9  cmp     rcx, rdx
0x18003faec  jz      loc_18008FB1C
0x18003faf2  test    byte ptr [rcx+1Ch], 1
0x18003faf6  jz      loc_18008FB1C
0x18003fafc  mov     rcx, [rcx+10h]
0x18003fb00  lea     r8, WPP_39e7268a77b0313df132bc71a3d61242_Traceguids
0x18003fb07  mov     edx, 0Dh
0x18003fb0c  mov     r9d, eax
0x18003fb0f  call    WPP_SF_d
0x18003fb14  nop
0x18003fb15  jmp     loc_18008FB1C
0x18003fb1a  mov     rax, cs:WPP_GLOBAL_Control
0x18003fb21  lea     rdx, WPP_GLOBAL_Control
0x18003fb28  cmp     rax, rdx
0x18003fb2b  jz      loc_18008FB26
0x18003fb31  test    byte ptr [rax+1Ch], 1
0x18003fb35  jz      loc_18008FB26
0x18003fb3b  call    cs:__imp_GetLastError
0x18003fb41  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb48  lea     r8, WPP_39e7268a77b0313df132bc71a3d61242_Traceguids
0x18003fb4f  mov     edx, 0Eh
0x18003fb54  mov     r9d, eax
0x18003fb57  mov     rcx, [rcx+10h]
0x18003fb5b  call    WPP_SF_d
0x18003fb60  nop
0x18003fb61  jmp     loc_18008FB26
0x18003fb66  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb6d  lea     rdx, WPP_GLOBAL_Control
0x18003fb74  cmp     rcx, rdx
0x18003fb77  jz      loc_18008FB39
0x18003fb7d  test    byte ptr [rcx+1Ch], 1
0x18003fb81  jz      loc_18008FB39
0x18003fb87  mov     rcx, [rcx+10h]
0x18003fb8b  lea     r8, WPP_39e7268a77b0313df132bc71a3d61242_Traceguids
0x18003fb92  mov     edx, 0Fh
0x18003fb97  call    WPP_SF_
0x18003fb9c  nop
0x18003fb9d  jmp     loc_18008FB39
0x18008fb1c  mov     eax, 80090308h
0x18008fb21  jmp     loc_18003FA96
0x18008fb26  mov     rcx, rsi; pCertContext
0x18008fb29  call    cs:__imp_CertFreeCertificateContext
0x18008fb2f  mov     ebp, 8009035Dh
0x18008fb34  jmp     loc_18003FA84
0x18008fb39  mov     ebp, 80090304h
0x18008fb3e  jmp     loc_18003FA84
```
