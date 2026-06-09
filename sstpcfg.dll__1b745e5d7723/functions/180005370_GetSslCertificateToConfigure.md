# GetSslCertificateToConfigure

- ea: `0x180005370`
- end: `0x180005828`
- name: `GetSslCertificateToConfigure`
- size: `1208`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180007450`

## callees

- `0x180005370`
- `0x1800070f0`
- `0x180007408`
- `0x18000a014`
- `0x18000a044`
- `0x18000a110`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000af10`
- `0x18000c010`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x18000578a`
- `CRYPT32!CertCloseStore` at `0x18000578a`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800054d0`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000580f`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800054d0`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000580f`
- `CRYPT32!CertNameToStrW` at `0x18000550d`
- `CRYPT32!CertNameToStrW` at `0x18000550d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180005651`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800056ec`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000574e`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180005651`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800056ec`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000574e`
- `CRYPT32!CertOpenStore` at `0x180005430`
- `CRYPT32!CertOpenStore` at `0x180005430`
- `CRYPT32!CertFreeCertificateContext` at `0x180005760`
- `CRYPT32!CertFreeCertificateContext` at `0x18000576e`
- `CRYPT32!CertFreeCertificateContext` at `0x18000577c`
- `CRYPT32!CertFreeCertificateContext` at `0x180005760`
- `CRYPT32!CertFreeCertificateContext` at `0x18000576e`
- `CRYPT32!CertFreeCertificateContext` at `0x18000577c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055dd`

## string_xrefs

- `0x180005489`: `Unable to open the certificate store...%d`

## pseudocode

```c
__int64 __fastcall GetSslCertificateToConfigure(PCCERT_CONTEXT *a1)
{
  HCERTSTORE v2; // rax
  void *v3; // r15
  DWORD v4; // ebx
  __int64 v5; // r8
  PCCERT_CONTEXT v6; // rdi
  __int64 v7; // r8
  __int64 v8; // rbx
  DWORD LastError; // eax
  __int64 v10; // r8
  DWORD v11; // eax
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[2044]; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR psz[1024]; // [rsp+840h] [rbp+740h] BYREF

  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17);
  }
  if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      *((_QWORD *)&xmmword_1800146E0 + 1),
      L"SetSslCertificate...Picking up the server authentication certificate from machine store");
  v2 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20004u, L"MY");
  v3 = v2;
  if ( v2 )
  {
    v6 = CertEnumCertificatesInStore(v2, 0);
    if ( v6 )
    {
      do
      {
        psz[0] = 0;
        if ( CertNameToStrW(0x10001u, &v6->pCertInfo->Subject, 3u, psz, 0x400u) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v7, psz);
          }
          if ( (_QWORD)xmmword_1800146E0 )
          {
            LOWORD(v13) = 0;
            FormatRRASErrorString(&v13, L"Checking certificate:%ws ...", psz);
            ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
              gSstpCfgEtwContext,
              xmmword_1800146E0,
              &v13);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            LastError = GetLastError();
            WPP_SF_d(v8, 20, v10, LastError);
          }
          if ( (_QWORD)xmmword_1800146E0 )
          {
            LOWORD(v13) = 0;
            v11 = GetLastError();
            FormatRRASErrorString(&v13, L"Unable to query current cert name: %d", v11);
            ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
              gSstpCfgEtwContext,
              xmmword_1800146E0,
              &v13);
          }
        }
        if ( (unsigned __int8)IsPrivateKeyPresent(v6) )
        {
          IsCertificateEKUServerAuth(v6);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24);
          }
          if ( (_QWORD)xmmword_1800146E0 )
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
              gSstpCfgEtwContext,
              xmmword_1800146E0,
              L"Skipping certificate as it doesn't have private key");
        }
        v6 = CertEnumCertificatesInStore(v3, v6);
      }
      while ( v6 );
      v4 = 0;
    }
    else
    {
      v4 = 0;
    }
    *a1 = CertDuplicateCertificateContext(0);
    CertCloseStore(v3, 2u);
  }
  else
  {
    v4 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v5, v4);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"Unable to open the certificate store...%d", v4);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v13);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180005370  mov     [rsp-8+arg_8], rbx
0x180005375  mov     [rsp-8+arg_10], rsi
0x18000537a  push    rbp
0x18000537b  push    rdi
0x18000537c  push    r12
0x18000537e  push    r14
0x180005380  push    r15
0x180005382  lea     rbp, [rsp-0F50h]
0x18000538a  mov     eax, 1050h
0x18000538f  call    _alloca_probe
0x180005394  sub     rsp, rax
0x180005397  mov     rax, cs:__security_cookie
0x18000539e  xor     rax, rsp
0x1800053a1  mov     [rbp+0F70h+var_30], rax
0x1800053a8  mov     r12, rcx
0x1800053ab  xor     eax, eax
0x1800053ad  lea     rcx, [rsp+1070h+var_102C]; void *
0x1800053b2  mov     [rsp+1070h+var_1030], eax
0x1800053b6  xor     edx, edx; Val
0x1800053b8  mov     r8d, 7FCh; Size
0x1800053be  call    memset_0
0x1800053c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053ca  lea     rbx, WPP_GLOBAL_Control
0x1800053d1  cmp     rcx, rbx
0x1800053d4  jz      short loc_1800053F0
0x1800053d6  test    byte ptr [rcx+1Ch], 40h
0x1800053da  jz      short loc_1800053F0
0x1800053dc  cmp     byte ptr [rcx+19h], 1
0x1800053e0  jb      short loc_1800053F0
0x1800053e2  mov     rcx, [rcx+10h]
0x1800053e6  mov     edx, 11h
0x1800053eb  call    WPP_SF_
0x1800053f0  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x1800053f7  test    rdx, rdx
0x1800053fa  jz      short loc_180005416
0x1800053fc  mov     rcx, cs:gSstpCfgEtwContext
0x180005403  lea     r8, aSetsslcertific; "SetSslCertificate...Picking up the serv"...
0x18000540a  mov     rax, cs:gSstpCfgTemplateFunc
0x180005411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005416  xor     edx, edx; dwEncodingType
0x180005418  lea     rax, aMy; "MY"
0x18000541f  mov     r9d, 20004h; dwFlags
0x180005425  mov     [rsp+1070h+pvPara], rax; pvPara
0x18000542a  xor     r8d, r8d; hCryptProv
0x18000542d  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180005430  call    cs:__imp_CertOpenStore
0x180005436  mov     r15, rax
0x180005439  test    rax, rax
0x18000543c  jnz     loc_1800054C6
0x180005442  call    cs:__imp_GetLastError
0x180005448  mov     ebx, eax
0x18000544a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005451  lea     rax, WPP_GLOBAL_Control
0x180005458  cmp     rcx, rax
0x18000545b  jz      short loc_180005479
0x18000545d  test    byte ptr [rcx+1Ch], 40h
0x180005461  jz      short loc_180005479
0x180005463  cmp     byte ptr [rcx+19h], 1
0x180005467  jb      short loc_180005479
0x180005469  mov     rcx, [rcx+10h]
0x18000546d  lea     edx, [r15+12h]
0x180005471  mov     r9d, ebx
0x180005474  call    WPP_SF_d
0x180005479  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180005481  jz      loc_180005790
0x180005487  xor     eax, eax
0x180005489  lea     rdx, aUnableToOpenTh_0; "Unable to open the certificate store..."...
0x180005490  mov     r8d, ebx
0x180005493  mov     word ptr [rsp+1070h+var_1030], ax
0x180005498  lea     rcx, [rsp+1070h+var_1030]
0x18000549d  call    FormatRRASErrorString
0x1800054a2  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800054a9  lea     r8, [rsp+1070h+var_1030]
0x1800054ae  mov     rcx, cs:gSstpCfgEtwContext
0x1800054b5  mov     rax, cs:gSstpCfgTemplateFunc
0x1800054bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054c1  jmp     loc_180005790
0x1800054c6  xor     edx, edx; pPrevCertContext
0x1800054c8  mov     rcx, r15; hCertStore
0x1800054cb  xor     esi, esi
0x1800054cd  xor     r14d, r14d
0x1800054d0  call    cs:__imp_CertEnumCertificatesInStore
0x1800054d6  mov     rdi, rax
0x1800054d9  test    rax, rax
0x1800054dc  jz      loc_180005741
0x1800054e2  xor     ecx, ecx
0x1800054e4  mov     dword ptr [rsp+1070h+pvPara], 400h; csz
0x1800054ec  mov     [rbp+0F70h+psz], cx
0x1800054f3  lea     r9, [rbp+0F70h+psz]; psz
0x1800054fa  mov     rdx, [rdi+18h]
0x1800054fe  mov     ecx, 10001h; dwCertEncodingType
0x180005503  add     rdx, 50h ; 'P'; pName
0x180005507  mov     r8d, 3; dwStrType
0x18000550d  call    cs:__imp_CertNameToStrW
0x180005513  test    eax, eax
0x180005515  jz      short loc_180005594
0x180005517  mov     rcx, cs:WPP_GLOBAL_Control
0x18000551e  cmp     rcx, rbx
0x180005521  jz      short loc_180005544
0x180005523  test    byte ptr [rcx+1Ch], 40h
0x180005527  jz      short loc_180005544
0x180005529  cmp     byte ptr [rcx+19h], 1
0x18000552d  jb      short loc_180005544
0x18000552f  mov     rcx, [rcx+10h]
0x180005533  lea     r9, [rbp+0F70h+psz]
0x18000553a  mov     edx, 13h
0x18000553f  call    WPP_SF_S
0x180005544  cmp     qword ptr cs:xmmword_1800146E0, rsi
0x18000554b  jz      loc_18000561D
0x180005551  xor     eax, eax
0x180005553  lea     r8, [rbp+0F70h+psz]
0x18000555a  lea     rdx, aCheckingCertif; "Checking certificate:%ws ..."
0x180005561  mov     word ptr [rsp+1070h+var_1030], ax
0x180005566  lea     rcx, [rsp+1070h+var_1030]
0x18000556b  call    FormatRRASErrorString
0x180005570  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180005577  lea     r8, [rsp+1070h+var_1030]
0x18000557c  mov     rcx, cs:gSstpCfgEtwContext
0x180005583  mov     rax, cs:gSstpCfgTemplateFunc
0x18000558a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000558f  jmp     loc_18000561D
0x180005594  mov     rbx, cs:WPP_GLOBAL_Control
0x18000559b  lea     rax, WPP_GLOBAL_Control
0x1800055a2  cmp     rbx, rax
0x1800055a5  jz      short loc_1800055CD
0x1800055a7  test    byte ptr [rbx+1Ch], 40h
0x1800055ab  jz      short loc_1800055CD
0x1800055ad  cmp     byte ptr [rbx+19h], 1
0x1800055b1  jb      short loc_1800055CD
0x1800055b3  mov     rbx, [rbx+10h]
0x1800055b7  call    cs:__imp_GetLastError
0x1800055bd  mov     edx, 14h
0x1800055c2  mov     rcx, rbx
0x1800055c5  mov     r9d, eax
0x1800055c8  call    WPP_SF_d
0x1800055cd  cmp     qword ptr cs:xmmword_1800146E0, rsi
0x1800055d4  jz      short loc_180005616
0x1800055d6  xor     eax, eax
0x1800055d8  mov     word ptr [rsp+1070h+var_1030], ax
0x1800055dd  call    cs:__imp_GetLastError
0x1800055e3  mov     r8d, eax
0x1800055e6  lea     rdx, aUnableToQueryC; "Unable to query current cert name: %d"
0x1800055ed  lea     rcx, [rsp+1070h+var_1030]
0x1800055f2  call    FormatRRASErrorString
0x1800055f7  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800055fe  lea     r8, [rsp+1070h+var_1030]
0x180005603  mov     rcx, cs:gSstpCfgEtwContext
0x18000560a  mov     rax, cs:gSstpCfgTemplateFunc
0x180005611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005616  lea     rbx, WPP_GLOBAL_Control
0x18000561d  mov     rcx, rdi
0x180005620  call    IsPrivateKeyPresent
0x180005625  test    al, al
0x180005627  jz      loc_1800057BD
0x18000562d  lea     rdx, [rsp+1070h+var_1040]
0x180005632  mov     [rsp+1070h+var_1040], esi
0x180005636  mov     rcx, rdi; pCertContext
0x180005639  call    IsCertificateEKUServerAuth
0x18000563e  cmp     [rsp+1070h+var_1040], 2
0x180005643  jnz     loc_1800056DE
0x180005649  test    r14, r14
0x18000564c  jnz     short loc_18000569C
0x18000564e  mov     rcx, rdi; pCertContext
0x180005651  call    cs:__imp_CertDuplicateCertificateContext
0x180005657  mov     r14, rax
0x18000565a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005661  cmp     rcx, rbx
0x180005664  jz      short loc_180005680
0x180005666  test    byte ptr [rcx+1Ch], 40h
0x18000566a  jz      short loc_180005680
0x18000566c  cmp     byte ptr [rcx+19h], 1
0x180005670  jb      short loc_180005680
0x180005672  mov     rcx, [rcx+10h]
0x180005676  mov     edx, 15h
0x18000567b  call    WPP_SF_
0x180005680  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180005687  test    rdx, rdx
0x18000568a  jz      loc_180005809
0x180005690  lea     r8, aPickingUpTheCu; "Picking up the current all purpose cert"...
0x180005697  jmp     loc_1800057F6
0x18000569c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056a3  cmp     rcx, rbx
0x1800056a6  jz      short loc_1800056C2
0x1800056a8  test    byte ptr [rcx+1Ch], 40h
0x1800056ac  jz      short loc_1800056C2
0x1800056ae  cmp     byte ptr [rcx+19h], 1
0x1800056b2  jb      short loc_1800056C2
0x1800056b4  mov     rcx, [rcx+10h]
0x1800056b8  mov     edx, 16h
0x1800056bd  call    WPP_SF_
0x1800056c2  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800056c9  test    rdx, rdx
0x1800056cc  jz      loc_180005809
0x1800056d2  lea     r8, aIgnoringTheAll; "Ignoring the all purpose cert"
0x1800056d9  jmp     loc_1800057F6
0x1800056de  cmp     [rsp+1070h+var_1040], 1
0x1800056e3  jnz     loc_180005809
0x1800056e9  mov     rcx, rdi; pCertContext
0x1800056ec  call    cs:__imp_CertDuplicateCertificateContext
0x1800056f2  mov     rsi, rax
0x1800056f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056fc  cmp     rcx, rbx
0x1800056ff  jz      short loc_18000571B
0x180005701  test    byte ptr [rcx+1Ch], 40h
0x180005705  jz      short loc_18000571B
0x180005707  cmp     byte ptr [rcx+19h], 1
0x18000570b  jb      short loc_18000571B
0x18000570d  mov     rcx, [rcx+10h]
0x180005711  mov     edx, 17h
0x180005716  call    WPP_SF_
0x18000571b  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180005722  test    rdx, rdx
0x180005725  jz      short loc_180005741
0x180005727  mov     rcx, cs:gSstpCfgEtwContext
0x18000572e  lea     r8, aFoundTheServer; "Found the server auth certificate"
0x180005735  mov     rax, cs:gSstpCfgTemplateFunc
0x18000573c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005741  xor     ebx, ebx
0x180005743  mov     rcx, rsi
0x180005746  test    rsi, rsi
0x180005749  jnz     short loc_18000574E
0x18000574b  mov     rcx, r14; pCertContext
0x18000574e  call    cs:__imp_CertDuplicateCertificateContext
0x180005754  mov     [r12], rax
0x180005758  test    rdi, rdi
0x18000575b  jz      short loc_180005766
0x18000575d  mov     rcx, rdi; pCertContext
0x180005760  call    cs:__imp_CertFreeCertificateContext
0x180005766  test    rsi, rsi
0x180005769  jz      short loc_180005774
0x18000576b  mov     rcx, rsi; pCertContext
0x18000576e  call    cs:__imp_CertFreeCertificateContext
0x180005774  test    r14, r14
0x180005777  jz      short loc_180005782
0x180005779  mov     rcx, r14; pCertContext
0x18000577c  call    cs:__imp_CertFreeCertificateContext
0x180005782  mov     edx, 2; dwFlags
0x180005787  mov     rcx, r15; hCertStore
0x18000578a  call    cs:__imp_CertCloseStore
0x180005790  mov     eax, ebx
0x180005792  mov     rcx, [rbp+0F70h+var_30]
0x180005799  xor     rcx, rsp; StackCookie
0x18000579c  call    __security_check_cookie
0x1800057a1  lea     r11, [rsp+1070h+var_20]
0x1800057a9  mov     rbx, [r11+38h]
0x1800057ad  mov     rsi, [r11+40h]
0x1800057b1  mov     rsp, r11
0x1800057b4  pop     r15
0x1800057b6  pop     r14
0x1800057b8  pop     r12
0x1800057ba  pop     rdi
0x1800057bb  pop     rbp
0x1800057bc  retn
0x1800057bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057c4  cmp     rcx, rbx
0x1800057c7  jz      short loc_1800057E3
0x1800057c9  test    byte ptr [rcx+1Ch], 40h
0x1800057cd  jz      short loc_1800057E3
0x1800057cf  cmp     byte ptr [rcx+19h], 1
0x1800057d3  jb      short loc_1800057E3
0x1800057d5  mov     rcx, [rcx+10h]
0x1800057d9  mov     edx, 18h
0x1800057de  call    WPP_SF_
0x1800057e3  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800057ea  test    rdx, rdx
0x1800057ed  jz      short loc_180005809
0x1800057ef  lea     r8, aSkippingCertif; "Skipping certificate as it doesn't have"...
0x1800057f6  mov     rcx, cs:gSstpCfgEtwContext
0x1800057fd  mov     rax, cs:gSstpCfgTemplateFunc
0x180005804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005809  mov     rdx, rdi; pPrevCertContext
0x18000580c  mov     rcx, r15; hCertStore
0x18000580f  call    cs:__imp_CertEnumCertificatesInStore
0x180005815  mov     rdi, rax
0x180005818  test    rax, rax
0x18000581b  jnz     loc_1800054E2
0x180005821  xor     ebx, ebx
0x180005823  jmp     loc_18000574B
```
