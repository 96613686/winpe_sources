# IsCertInStore(_CERT_CONTEXT const * const,wchar_t *,bool *)

- ea: `0x1800115f0`
- end: `0x1800117df`
- name: `?IsCertInStore@@YAJQEBU_CERT_CONTEXT@@PEA_WPEA_N@Z`
- size: `495`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *const, wchar_t *, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180012784`
- `0x180012ab0`

## callees

- `0x18000956c`
- `0x1800115f0`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011751`
- `CRYPT32!CertOpenStore` at `0x1800116c4`
- `CRYPT32!CertOpenStore` at `0x1800116c4`
- `CRYPT32!CertFindCertificateInStore` at `0x18001173c`
- `CRYPT32!CertFindCertificateInStore` at `0x18001173c`
- `CRYPT32!CertCloseStore` at `0x1800117a7`
- `CRYPT32!CertCloseStore` at `0x1800117a7`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180011648`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180011648`
- `CRYPT32!CertFreeCertificateContext` at `0x1800117b5`
- `CRYPT32!CertFreeCertificateContext` at `0x1800117b5`
- `CRYPT32!CertControlStore` at `0x180011715`
- `CRYPT32!CertControlStore` at `0x180011715`

## pseudocode

```c
__int64 __fastcall IsCertInStore(const struct _CERT_CONTEXT *const a1, wchar_t *a2, bool *a3)
{
  signed int v4; // eax
  signed int v5; // ebx
  HCERTSTORE v6; // rax
  void *v7; // rsi
  signed int v8; // eax
  const CERT_CONTEXT *CertificateInStore; // rbp
  signed int LastError; // eax
  _QWORD pvFindPara[2]; // [rsp+40h] [rbp-48h] BYREF
  __int128 v13; // [rsp+50h] [rbp-38h] BYREF
  int v14; // [rsp+60h] [rbp-28h]

  pvFindPara[0] = 20;
  *a3 = 0;
  v14 = 0;
  pvFindPara[1] = &v13;
  v13 = 0;
  if ( CertGetCertificateContextProperty(a1, 3u, &v13, (DWORD *)pvFindPara) )
  {
    if ( LODWORD(pvFindPara[0]) != 20 )
      WUTrace(0, 0, 32, 3);
    v6 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x2C000u, aTrustedpublish);
    v7 = v6;
    if ( v6 )
    {
      CertControlStore(v6, 0, 4u, 0);
      CertificateInStore = CertFindCertificateInStore(v7, 0, 0, 0x10000u, pvFindPara, 0);
      if ( CertificateInStore )
      {
        v5 = 0;
        *a3 = 1;
      }
      else
      {
        LastError = GetLastError();
        v5 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v5 = LastError;
        if ( v5 < 0 )
        {
          if ( v5 == -2146885628 )
          {
            v5 = 0;
            *a3 = 0;
          }
        }
        else
        {
          v5 = -2147418113;
        }
      }
      WUTrace(0, 0, 32, 5);
      CertCloseStore(v7, 0);
      if ( CertificateInStore )
        CertFreeCertificateContext(CertificateInStore);
    }
    else
    {
      v8 = GetLastError();
      v5 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 <= 0 )
        v5 = v8;
      if ( v5 < 0 )
      {
        if ( v5 == -2147024894 )
        {
          v5 = 0;
          *a3 = 0;
        }
      }
      else
      {
        return (unsigned int)-2147418113;
      }
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 <= 0 )
      v5 = v4;
    if ( v5 >= 0 )
      return (unsigned int)-2147418113;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800115f0  mov     r11, rsp
0x1800115f3  mov     [r11+10h], rbx
0x1800115f7  mov     [r11+20h], rbp
0x1800115fb  push    rsi
0x1800115fc  push    rdi
0x1800115fd  push    r12
0x1800115ff  sub     rsp, 70h
0x180011603  mov     rax, cs:__security_cookie
0x18001160a  xor     rax, rsp
0x18001160d  mov     [rsp+88h+var_20], rax
0x180011612  xor     eax, eax
0x180011614  mov     qword ptr [r11-48h], 14h
0x18001161c  mov     [r8], al
0x18001161f  lea     r9, [r11-48h]; pcbData
0x180011623  mov     [rsp+88h+var_28], eax
0x180011627  mov     rdi, r8
0x18001162a  xorps   xmm0, xmm0
0x18001162d  lea     rax, [r11-38h]
0x180011631  mov     ebx, 14h
0x180011636  mov     [r11-40h], rax
0x18001163a  lea     r8, [r11-38h]; pvData
0x18001163e  movups  [rsp+88h+var_38], xmm0
0x180011643  lea     esi, [rbx-11h]
0x180011646  mov     edx, esi; dwPropId
0x180011648  call    cs:__imp_CertGetCertificateContextProperty
0x18001164e  test    eax, eax
0x180011650  jnz     short loc_180011675
0x180011652  call    cs:__imp_GetLastError
0x180011658  movzx   ebx, ax
0x18001165b  or      ebx, 80070000h
0x180011661  test    eax, eax
0x180011663  cmovle  ebx, eax
0x180011666  mov     eax, 8000FFFFh
0x18001166b  test    ebx, ebx
0x18001166d  cmovns  ebx, eax
0x180011670  jmp     loc_1800117BB
0x180011675  mov     eax, [rsp+88h+pvFindPara]
0x180011679  cmp     eax, ebx
0x18001167b  jz      short loc_1800116AA
0x18001167d  mov     [rsp+88h+var_50], ebx
0x180011681  xor     edx, edx
0x180011683  mov     dword ptr [rsp+88h+var_58], eax
0x180011687  mov     r9d, esi
0x18001168a  lea     rax, aCertgetcertifi_1; "CertGetCertificateContextProperty() wit"...
0x180011691  xor     ecx, ecx
0x180011693  mov     [rsp+88h+pPrevCertContext], rax
0x180011698  lea     r8d, [rdx+20h]
0x18001169c  mov     [rsp+88h+pvPara], 0
0x1800116a5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800116aa  xor     edx, edx; dwEncodingType
0x1800116ac  lea     r12, aTrustedpublish; "TrustedPublisher"
0x1800116b3  mov     r9d, 2C000h; dwFlags
0x1800116b9  mov     [rsp+88h+pvPara], r12; pvPara
0x1800116be  xor     r8d, r8d; hCryptProv
0x1800116c1  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800116c4  call    cs:__imp_CertOpenStore
0x1800116ca  mov     rsi, rax
0x1800116cd  test    rax, rax
0x1800116d0  jnz     short loc_180011709
0x1800116d2  call    cs:__imp_GetLastError
0x1800116d8  movzx   ebx, ax
0x1800116db  or      ebx, 80070000h
0x1800116e1  test    eax, eax
0x1800116e3  cmovle  ebx, eax
0x1800116e6  test    ebx, ebx
0x1800116e8  js      short loc_1800116F4
0x1800116ea  mov     ebx, 8000FFFFh
0x1800116ef  jmp     loc_1800117BB
0x1800116f4  cmp     ebx, 80070002h
0x1800116fa  jnz     loc_1800117BB
0x180011700  xor     ebx, ebx
0x180011702  mov     [rdi], bl
0x180011704  jmp     loc_1800117BB
0x180011709  xor     r9d, r9d; pvCtrlPara
0x18001170c  xor     edx, edx; dwFlags
0x18001170e  mov     rcx, rsi; hCertStore
0x180011711  lea     r8d, [r9+4]; dwCtrlType
0x180011715  call    cs:__imp_CertControlStore
0x18001171b  lea     rax, [rsp+88h+pvFindPara]
0x180011720  mov     [rsp+88h+pPrevCertContext], 0; pPrevCertContext
0x180011729  mov     r9d, 10000h; dwFindType
0x18001172f  mov     [rsp+88h+pvPara], rax; pvFindPara
0x180011734  xor     r8d, r8d; dwFindFlags
0x180011737  xor     edx, edx; dwCertEncodingType
0x180011739  mov     rcx, rsi; hCertStore
0x18001173c  call    cs:__imp_CertFindCertificateInStore
0x180011742  mov     rbp, rax
0x180011745  test    rax, rax
0x180011748  jz      short loc_180011751
0x18001174a  xor     ebx, ebx
0x18001174c  mov     byte ptr [rdi], 1
0x18001174f  jmp     short loc_18001177C
0x180011751  call    cs:__imp_GetLastError
0x180011757  movzx   ebx, ax
0x18001175a  or      ebx, 80070000h
0x180011760  test    eax, eax
0x180011762  cmovle  ebx, eax
0x180011765  test    ebx, ebx
0x180011767  js      short loc_180011770
0x180011769  mov     ebx, 8000FFFFh
0x18001176e  jmp     short loc_18001177C
0x180011770  cmp     ebx, 80092004h
0x180011776  jnz     short loc_18001177C
0x180011778  xor     ebx, ebx
0x18001177a  mov     [rdi], bl
0x18001177c  xor     edx, edx
0x18001177e  mov     [rsp+88h+var_58], r12
0x180011783  lea     rax, aExitingIscerti; "Exiting IsCertInStore() for %ws with re"...
0x18001178a  xor     ecx, ecx
0x18001178c  mov     [rsp+88h+pPrevCertContext], rax
0x180011791  mov     dword ptr [rsp+88h+pvPara], ebx
0x180011795  lea     r9d, [rdx+5]
0x180011799  lea     r8d, [rdx+20h]
0x18001179d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800117a2  xor     edx, edx; dwFlags
0x1800117a4  mov     rcx, rsi; hCertStore
0x1800117a7  call    cs:__imp_CertCloseStore
0x1800117ad  test    rbp, rbp
0x1800117b0  jz      short loc_1800117BB
0x1800117b2  mov     rcx, rbp; pCertContext
0x1800117b5  call    cs:__imp_CertFreeCertificateContext
0x1800117bb  mov     eax, ebx
0x1800117bd  mov     rcx, [rsp+88h+var_20]
0x1800117c2  xor     rcx, rsp; StackCookie
0x1800117c5  call    __security_check_cookie
0x1800117ca  lea     r11, [rsp+88h+var_18]
0x1800117cf  mov     rbx, [r11+28h]
0x1800117d3  mov     rbp, [r11+38h]
0x1800117d7  mov     rsp, r11
0x1800117da  pop     r12
0x1800117dc  pop     rdi
0x1800117dd  pop     rsi
0x1800117de  retn
```
