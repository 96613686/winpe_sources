# SslMapCertToUserPac(_SSL_CERT_LOGON_REQ *,ulong,uchar * *,ulong *,ushort * *)

- ea: `0x180065764`
- end: `0x180065c07`
- name: `?SslMapCertToUserPac@@YAJPEAU_SSL_CERT_LOGON_REQ@@KPEAPEAEPEAKPEAPEAG@Z`
- size: `1187`
- prototype: `int(struct _SSL_CERT_LOGON_REQ *, unsigned int, unsigned __int8 **, unsigned int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180064238`
- `0x180064bc8`

## callees

- `0x180021da8`
- `0x180057c8c`
- `0x180065764`
- `0x180066750`
- `0x180066a98`
- `0x1800670e4`
- `0x18006fd20`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x180065bba`
- `CRYPT32!CertFreeCertificateContext` at `0x180065bba`
- `CRYPT32!CertCreateCertificateContext` at `0x18006580c`
- `CRYPT32!CertCreateCertificateContext` at `0x18006580c`

## pseudocode

```c
__int64 __fastcall SslMapCertToUserPac(
        struct _SSL_CERT_LOGON_REQ *a1,
        unsigned int a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int16 **a5)
{
  unsigned __int64 v7; // rbp
  __int64 v9; // rcx
  DWORD v10; // r8d
  PCCERT_CONTEXT CertificateContext; // r13
  unsigned int v12; // ebx
  int v13; // eax
  CCipherMill *v14; // rcx
  __int64 v15; // rdx
  CCipherMill *v16; // r10
  int v17; // r15d
  int v18; // eax
  unsigned __int16 v19; // cx
  int v20; // eax
  __int64 i; // rsi
  __int64 v22; // rcx
  SIZE_T v23; // rdx
  int v24; // eax
  int v25; // eax

  v7 = a2;
  *a5 = 0;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids);
  if ( (unsigned int)(v7 - 32) > 0xFFE0 )
    return 3221225485LL;
  if ( *((_DWORD *)a1 + 1) > (unsigned int)v7 )
    return 3221225485LL;
  v9 = *((unsigned int *)a1 + 2);
  if ( (unsigned int)v9 > (unsigned int)v7 )
    return 3221225485LL;
  v10 = *((_DWORD *)a1 + 3);
  if ( v10 > 0x10000 || v10 + (unsigned int)v9 > (unsigned int)v7 )
    return 3221225485LL;
  CertificateContext = CertCreateCertificateContext(1u, (const BYTE *)a1 + v9, v10);
  if ( CertificateContext )
  {
    v12 = -1073741715;
    if ( (*((_BYTE *)a1 + 16) & 0x10) != 0 && (g_dwCertMappingMethods & 4) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids);
      }
      v13 = SslTryUpn(CertificateContext, a3, a4, a5);
      v12 = v13;
      if ( v13 >= 0 || *a5 )
      {
        v19 = 16;
        goto LABEL_37;
      }
      if ( v13 == -1073740943 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        {
          goto LABEL_78;
        }
        v15 = 21;
        goto LABEL_21;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      {
LABEL_26:
        v17 = -1073741275;
        if ( (*((_BYTE *)a1 + 16) & 0x20) == 0 || (g_dwCertMappingMethods & 1) == 0 )
          goto LABEL_42;
        if ( v16 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x100) != 0 )
          WPP_SF_(*((_QWORD *)v16 + 2), 23, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids);
        v18 = SslTryCompoundName(CertificateContext, a3, a4, a5);
        v12 = v18;
        if ( v18 < 0 && !*a5 )
        {
          if ( v18 == -1073740943 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
            {
              goto LABEL_78;
            }
            v15 = 24;
            goto LABEL_21;
          }
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              WPP_e1738149d20f31dfe7380947af7f2303_Traceguids,
              (unsigned int)v18);
            v16 = WPP_GLOBAL_Control;
          }
          v17 = v12;
LABEL_42:
          if ( (*((_BYTE *)a1 + 16) & 0x40) != 0 && (g_dwCertMappingMethods & 2) != 0 )
          {
            if ( v16 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x100) != 0 )
              WPP_SF_(*((_QWORD *)v16 + 2), 26, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids);
            if ( *((char *)a1 + 16) < 0 && (v20 = *((_DWORD *)a1 + 5)) != 0 )
            {
              if ( 8 * (unsigned __int64)(unsigned int)(v20 - 1) + 32 > v7 )
              {
                v12 = -1073741811;
                goto LABEL_78;
              }
              for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 5); i = (unsigned int)(i + 1) )
              {
                v22 = *((unsigned int *)a1 + 2 * i + 6);
                if ( (unsigned int)v22 > (unsigned int)v7 )
                  return 3221225485LL;
                v23 = *((unsigned int *)a1 + 2 * i + 7);
                if ( (unsigned int)v23 > 0x10000 || (int)v23 + (int)v22 > (unsigned int)v7 )
                  return 3221225485LL;
                v24 = SslTryIssuer((unsigned __int8 *)a1 + v22, v23, a3, a4, a5);
                v12 = v24;
                if ( v24 >= 0 || *a5 )
                  goto LABEL_63;
                if ( v24 == -1073740943 )
                {
                  v14 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
                  {
                    v15 = 27;
                    goto LABEL_21;
                  }
                  goto LABEL_78;
                }
              }
            }
            else
            {
              v25 = SslTryIssuer(
                      CertificateContext->pCertInfo->Issuer.pbData,
                      CertificateContext->pCertInfo->Issuer.cbData,
                      a3,
                      a4,
                      a5);
              v12 = v25;
              if ( v25 >= 0 || *a5 )
              {
LABEL_63:
                CSchannelTelemetryContext::LogRCMPUsage(4u);
                goto LABEL_78;
              }
              if ( v25 == -1073740943 )
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
                {
                  goto LABEL_78;
                }
                v15 = 28;
LABEL_21:
                WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids, 3221226353LL);
LABEL_78:
                CertFreeCertificateContext(CertificateContext);
                goto LABEL_79;
              }
            }
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids, v12);
            }
          }
          if ( v12 == -1073741771 || v17 == -1073741771 )
          {
            v12 = -2146892985;
          }
          else if ( v12 != -1073741801 )
          {
            v12 = -1073741715;
          }
          goto LABEL_78;
        }
        v19 = 8;
LABEL_37:
        CSchannelTelemetryContext::LogRCMPUsage(v19);
        goto LABEL_78;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_e1738149d20f31dfe7380947af7f2303_Traceguids,
        (unsigned int)v13);
    }
    v16 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  v12 = -1073741801;
LABEL_79:
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180065764  mov     [rsp+arg_10], r8
0x180065769  push    rbx
0x18006576a  push    rbp
0x18006576b  push    rsi
0x18006576c  push    rdi
0x18006576d  push    r12
0x18006576f  push    r13
0x180065771  push    r14
0x180065773  push    r15
0x180065775  sub     rsp, 38h
0x180065779  mov     r14, [rsp+78h+arg_20]
0x180065781  mov     r12, r9
0x180065784  mov     rsi, r8
0x180065787  mov     ebp, edx
0x180065789  mov     rdi, rcx
0x18006578c  mov     qword ptr [r14], 0
0x180065793  mov     rcx, cs:WPP_GLOBAL_Control
0x18006579a  lea     r15, WPP_GLOBAL_Control
0x1800657a1  cmp     rcx, r15
0x1800657a4  jz      short loc_1800657C4
0x1800657a6  test    dword ptr [rcx+1Ch], 100h
0x1800657ad  jz      short loc_1800657C4
0x1800657af  mov     rcx, [rcx+10h]
0x1800657b3  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x1800657ba  mov     edx, 13h
0x1800657bf  call    WPP_SF_
0x1800657c4  lea     eax, [rbp-20h]
0x1800657c7  cmp     eax, 0FFE0h
0x1800657cc  ja      loc_180065BF1
0x1800657d2  cmp     [rdi+4], ebp
0x1800657d5  ja      loc_180065BF1
0x1800657db  mov     ecx, [rdi+8]
0x1800657de  cmp     ecx, ebp
0x1800657e0  ja      loc_180065BF1
0x1800657e6  mov     r8d, [rdi+0Ch]; cbCertEncoded
0x1800657ea  cmp     r8d, 10000h
0x1800657f1  ja      loc_180065BF1
0x1800657f7  lea     eax, [r8+rcx]
0x1800657fb  cmp     eax, ebp
0x1800657fd  ja      loc_180065BF1
0x180065803  lea     rdx, [rdi+rcx]; pbCertEncoded
0x180065807  mov     ecx, 1; dwCertEncodingType
0x18006580c  call    cs:__imp_CertCreateCertificateContext
0x180065812  mov     r13, rax
0x180065815  test    rax, rax
0x180065818  jnz     short loc_180065824
0x18006581a  mov     ebx, 0C0000017h
0x18006581f  jmp     loc_180065BC0
0x180065824  test    byte ptr [rdi+10h], 10h
0x180065828  mov     ebx, 0C000006Dh
0x18006582d  setnz   cl
0x180065830  test    byte ptr cs:?g_dwCertMappingMethods@@3KA, 4; ulong g_dwCertMappingMethods
0x180065837  setnz   al
0x18006583a  test    al, cl
0x18006583c  jz      loc_180065903
0x180065842  mov     rcx, cs:WPP_GLOBAL_Control
0x180065849  cmp     rcx, r15
0x18006584c  jz      short loc_18006586C
0x18006584e  test    dword ptr [rcx+1Ch], 100h
0x180065855  jz      short loc_18006586C
0x180065857  mov     rcx, [rcx+10h]
0x18006585b  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x180065862  mov     edx, 14h
0x180065867  call    WPP_SF_
0x18006586c  mov     r9, r14; unsigned __int16 **
0x18006586f  mov     r8, r12; unsigned int *
0x180065872  mov     rdx, rsi; unsigned __int8 **
0x180065875  mov     rcx, r13; struct _CERT_CONTEXT *
0x180065878  call    ?SslTryUpn@@YAJPEBU_CERT_CONTEXT@@PEAPEAEPEAKPEAPEAG@Z; SslTryUpn(_CERT_CONTEXT const *,uchar * *,ulong *,ushort * *)
0x18006587d  mov     ebx, eax
0x18006587f  test    eax, eax
0x180065881  jns     loc_1800659A7
0x180065887  cmp     qword ptr [r14], 0
0x18006588b  jnz     loc_1800659A7
0x180065891  cmp     eax, 0C0000371h
0x180065896  jnz     short loc_1800658D5
0x180065898  mov     rcx, cs:WPP_GLOBAL_Control
0x18006589f  cmp     rcx, r15
0x1800658a2  jz      loc_180065BB7
0x1800658a8  test    dword ptr [rcx+1Ch], 100h
0x1800658af  jz      loc_180065BB7
0x1800658b5  mov     edx, 15h
0x1800658ba  mov     rcx, [rcx+10h]
0x1800658be  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x1800658c5  mov     r9d, 0C0000371h
0x1800658cb  call    WPP_SF_d
0x1800658d0  jmp     loc_180065BB7
0x1800658d5  mov     r10, cs:WPP_GLOBAL_Control
0x1800658dc  cmp     r10, r15
0x1800658df  jz      short loc_18006590A
0x1800658e1  test    dword ptr [r10+1Ch], 100h
0x1800658e9  jz      short loc_18006590A
0x1800658eb  mov     rcx, [r10+10h]
0x1800658ef  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x1800658f6  mov     edx, 16h
0x1800658fb  mov     r9d, eax
0x1800658fe  call    WPP_SF_d
0x180065903  mov     r10, cs:WPP_GLOBAL_Control
0x18006590a  test    byte ptr [rdi+10h], 20h
0x18006590e  mov     r15d, 0C0000225h
0x180065914  setnz   cl
0x180065917  test    byte ptr cs:?g_dwCertMappingMethods@@3KA, 1; ulong g_dwCertMappingMethods
0x18006591e  setnz   al
0x180065921  test    al, cl
0x180065923  jz      loc_1800659EE
0x180065929  lea     r15, WPP_GLOBAL_Control
0x180065930  cmp     r10, r15
0x180065933  jz      short loc_180065954
0x180065935  test    dword ptr [r10+1Ch], 100h
0x18006593d  jz      short loc_180065954
0x18006593f  mov     rcx, [r10+10h]
0x180065943  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x18006594a  mov     edx, 17h
0x18006594f  call    WPP_SF_
0x180065954  mov     r9, r14; unsigned __int16 **
0x180065957  mov     r8, r12; unsigned int *
0x18006595a  mov     rdx, rsi; unsigned __int8 **
0x18006595d  mov     rcx, r13; struct _CERT_CONTEXT *
0x180065960  call    ?SslTryCompoundName@@YAJPEBU_CERT_CONTEXT@@PEAPEAEPEAKPEAPEAG@Z; SslTryCompoundName(_CERT_CONTEXT const *,uchar * *,ulong *,ushort * *)
0x180065965  mov     ebx, eax
0x180065967  test    eax, eax
0x180065969  jns     loc_180065A60
0x18006596f  cmp     qword ptr [r14], 0
0x180065973  jnz     loc_180065A60
0x180065979  cmp     eax, 0C0000371h
0x18006597e  jnz     short loc_1800659B6
0x180065980  mov     rcx, cs:WPP_GLOBAL_Control
0x180065987  cmp     rcx, r15
0x18006598a  jz      loc_180065BB7
0x180065990  test    dword ptr [rcx+1Ch], 100h
0x180065997  jz      loc_180065BB7
0x18006599d  mov     edx, 18h
0x1800659a2  jmp     loc_1800658BA
0x1800659a7  mov     ecx, 10h; unsigned __int16
0x1800659ac  call    ?LogRCMPUsage@CSchannelTelemetryContext@@SAXG@Z; CSchannelTelemetryContext::LogRCMPUsage(ushort)
0x1800659b1  jmp     loc_180065BB7
0x1800659b6  mov     r10, cs:WPP_GLOBAL_Control
0x1800659bd  cmp     r10, r15
0x1800659c0  jz      short loc_1800659EB
0x1800659c2  test    dword ptr [r10+1Ch], 100h
0x1800659ca  jz      short loc_1800659EB
0x1800659cc  mov     rcx, [r10+10h]
0x1800659d0  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x1800659d7  mov     edx, 19h
0x1800659dc  mov     r9d, ebx
0x1800659df  call    WPP_SF_d
0x1800659e4  mov     r10, cs:WPP_GLOBAL_Control
0x1800659eb  mov     r15d, ebx
0x1800659ee  test    byte ptr [rdi+10h], 40h
0x1800659f2  setnz   cl
0x1800659f5  test    byte ptr cs:?g_dwCertMappingMethods@@3KA, 2; ulong g_dwCertMappingMethods
0x1800659fc  setnz   al
0x1800659ff  test    al, cl
0x180065a01  jz      loc_180065B90
0x180065a07  lea     rax, WPP_GLOBAL_Control
0x180065a0e  cmp     r10, rax
0x180065a11  jz      short loc_180065A32
0x180065a13  test    dword ptr [r10+1Ch], 100h
0x180065a1b  jz      short loc_180065A32
0x180065a1d  mov     rcx, [r10+10h]
0x180065a21  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x180065a28  mov     edx, 1Ah
0x180065a2d  call    WPP_SF_
0x180065a32  test    byte ptr [rdi+10h], 80h
0x180065a36  jz      loc_180065B08
0x180065a3c  mov     eax, [rdi+14h]
0x180065a3f  test    eax, eax
0x180065a41  jz      loc_180065B08
0x180065a47  dec     eax
0x180065a49  lea     rcx, ds:20h[rax*8]
0x180065a51  cmp     rcx, rbp
0x180065a54  jbe     short loc_180065A6A
0x180065a56  mov     ebx, 0C000000Dh
0x180065a5b  jmp     loc_180065BB0
0x180065a60  mov     ecx, 8
0x180065a65  jmp     loc_1800659AC
0x180065a6a  xor     esi, esi
0x180065a6c  cmp     esi, [rdi+14h]
0x180065a6f  jnb     loc_180065B5C
0x180065a75  mov     ecx, [rdi+rsi*8+18h]
0x180065a79  cmp     ecx, ebp
0x180065a7b  ja      loc_180065BF1
0x180065a81  mov     edx, [rdi+rsi*8+1Ch]; uBytes
0x180065a85  cmp     edx, 10000h
0x180065a8b  ja      loc_180065BF1
0x180065a91  lea     eax, [rdx+rcx]
0x180065a94  cmp     eax, ebp
0x180065a96  ja      loc_180065BF1
0x180065a9c  mov     r8, [rsp+78h+arg_10]; unsigned __int8 **
0x180065aa4  add     rcx, rdi; unsigned __int8 *
0x180065aa7  mov     r9, r12; unsigned int *
0x180065aaa  mov     [rsp+78h+var_58], r14; unsigned __int16 **
0x180065aaf  call    ?SslTryIssuer@@YAJPEAEKPEAPEAEPEAKPEAPEAG@Z; SslTryIssuer(uchar *,ulong,uchar * *,ulong *,ushort * *)
0x180065ab4  mov     ebx, eax
0x180065ab6  test    eax, eax
0x180065ab8  jns     short loc_180065AF9
0x180065aba  cmp     qword ptr [r14], 0
0x180065abe  jnz     short loc_180065AF9
0x180065ac0  cmp     eax, 0C0000371h
0x180065ac5  jz      short loc_180065ACB
0x180065ac7  inc     esi
0x180065ac9  jmp     short loc_180065A6C
0x180065acb  mov     rcx, cs:WPP_GLOBAL_Control
0x180065ad2  lea     r15, WPP_GLOBAL_Control
0x180065ad9  cmp     rcx, r15
0x180065adc  jz      loc_180065BB7
0x180065ae2  test    dword ptr [rcx+1Ch], 100h
0x180065ae9  jz      loc_180065BB7
0x180065aef  mov     edx, 1Bh
0x180065af4  jmp     loc_1800658BA
0x180065af9  mov     ecx, 4; unsigned __int16
0x180065afe  call    ?LogRCMPUsage@CSchannelTelemetryContext@@SAXG@Z; CSchannelTelemetryContext::LogRCMPUsage(ushort)
0x180065b03  jmp     loc_180065BB0
0x180065b08  mov     rcx, [r13+18h]
0x180065b0c  mov     r9, r12; unsigned int *
0x180065b0f  mov     r8, rsi; unsigned __int8 **
0x180065b12  mov     [rsp+78h+var_58], r14; unsigned __int16 **
0x180065b17  mov     edx, [rcx+30h]; uBytes
0x180065b1a  mov     rcx, [rcx+38h]; unsigned __int8 *
0x180065b1e  call    ?SslTryIssuer@@YAJPEAEKPEAPEAEPEAKPEAPEAG@Z; SslTryIssuer(uchar *,ulong,uchar * *,ulong *,ushort * *)
0x180065b23  mov     ebx, eax
0x180065b25  test    eax, eax
0x180065b27  jns     short loc_180065AF9
0x180065b29  cmp     qword ptr [r14], 0
0x180065b2d  jnz     short loc_180065AF9
0x180065b2f  cmp     eax, 0C0000371h
0x180065b34  jnz     short loc_180065B5C
0x180065b36  mov     rcx, cs:WPP_GLOBAL_Control
0x180065b3d  lea     r15, WPP_GLOBAL_Control
0x180065b44  cmp     rcx, r15
0x180065b47  jz      short loc_180065BB7
0x180065b49  test    dword ptr [rcx+1Ch], 100h
0x180065b50  jz      short loc_180065BB7
0x180065b52  mov     edx, 1Ch
0x180065b57  jmp     loc_1800658BA
0x180065b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180065b63  lea     rax, WPP_GLOBAL_Control
0x180065b6a  cmp     rcx, rax
0x180065b6d  jz      short loc_180065B90
0x180065b6f  test    dword ptr [rcx+1Ch], 100h
0x180065b76  jz      short loc_180065B90
0x180065b78  mov     rcx, [rcx+10h]
0x180065b7c  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x180065b83  mov     edx, 1Dh
0x180065b88  mov     r9d, ebx
0x180065b8b  call    WPP_SF_d
0x180065b90  mov     eax, 0C0000035h
0x180065b95  cmp     ebx, eax
0x180065b97  jz      short loc_180065BAB
0x180065b99  cmp     r15d, eax
0x180065b9c  jz      short loc_180065BAB
0x180065b9e  cmp     ebx, 0C0000017h
0x180065ba4  jz      short loc_180065BB0
0x180065ba6  lea     ebx, [rax+38h]
0x180065ba9  jmp     short loc_180065BB0
0x180065bab  mov     ebx, 80090347h
0x180065bb0  lea     r15, WPP_GLOBAL_Control
0x180065bb7  mov     rcx, r13; pCertContext
0x180065bba  call    cs:__imp_CertFreeCertificateContext
0x180065bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180065bc7  cmp     rcx, r15
0x180065bca  jz      short loc_180065BED
0x180065bcc  test    dword ptr [rcx+1Ch], 100h
0x180065bd3  jz      short loc_180065BED
0x180065bd5  mov     rcx, [rcx+10h]
0x180065bd9  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x180065be0  mov     edx, 1Eh
0x180065be5  mov     r9d, ebx
0x180065be8  call    WPP_SF_d
0x180065bed  mov     eax, ebx
0x180065bef  jmp     short loc_180065BF6
0x180065bf1  mov     eax, 0C000000Dh
0x180065bf6  add     rsp, 38h
0x180065bfa  pop     r15
0x180065bfc  pop     r14
0x180065bfe  pop     r13
0x180065c00  pop     r12
0x180065c02  pop     rdi
0x180065c03  pop     rsi
0x180065c04  pop     rbp
0x180065c05  pop     rbx
0x180065c06  retn
```
