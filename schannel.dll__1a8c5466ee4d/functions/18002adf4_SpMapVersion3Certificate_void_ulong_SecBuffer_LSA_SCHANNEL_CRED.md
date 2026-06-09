# SpMapVersion3Certificate(void *,ulong,_SecBuffer *,LSA_SCHANNEL_CRED *)

- ea: `0x18002adf4`
- end: `0x18002b5e2`
- name: `?SpMapVersion3Certificate@@YAJPEAXKPEAU_SecBuffer@@PEAULSA_SCHANNEL_CRED@@@Z`
- size: `2030`
- prototype: `int(void *, unsigned int, struct _SecBuffer *, struct LSA_SCHANNEL_CRED *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18002b800`

## callees

- `0x180011f40`
- `0x180012d10`
- `0x180014240`
- `0x180021da8`
- `0x180021e64`
- `0x180021eb0`
- `0x18002acc0`
- `0x18002adf4`
- `0x180036550`
- `0x180057c8c`
- `0x18005a160`
- `0x18005c3a0`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b38d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b38d`
- `CRYPT32!CertOpenStore` at `0x18002b136`
- `CRYPT32!CertOpenStore` at `0x18002b2ad`
- `CRYPT32!CertOpenStore` at `0x18002b484`
- `CRYPT32!CertOpenStore` at `0x18002b136`
- `CRYPT32!CertOpenStore` at `0x18002b2ad`
- `CRYPT32!CertOpenStore` at `0x18002b484`
- `CRYPT32!CertCloseStore` at `0x18002af99`
- `CRYPT32!CertCloseStore` at `0x18002b305`
- `CRYPT32!CertCloseStore` at `0x18002b36a`
- `CRYPT32!CertCloseStore` at `0x18002af99`
- `CRYPT32!CertCloseStore` at `0x18002b305`
- `CRYPT32!CertCloseStore` at `0x18002b36a`
- `CRYPT32!CertAddSerializedElementToStore` at `0x18002b1f2`
- `CRYPT32!CertAddSerializedElementToStore` at `0x18002b1f2`
- `CRYPT32!CertFreeCertificateContext` at `0x18002b3cb`
- `CRYPT32!CertFreeCertificateContext` at `0x18002b3cb`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18002b2c5`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18002b2c5`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18002b2e6`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18002b2e6`

## pseudocode

```c
__int64 __fastcall SpMapVersion3Certificate(void *a1, int a2, struct _SecBuffer *a3, struct LSA_SCHANNEL_CRED *a4)
{
  int v4; // r12d
  unsigned int v6; // ebx
  void *v9; // r14
  int v10; // esi
  __int64 (__fastcall *v11)(_QWORD, __int64, _BYTE *, void *); // rax
  int v12; // ebx
  unsigned int v13; // r13d
  __int64 v14; // rax
  __int64 v15; // r14
  void *v16; // rsi
  unsigned int *pvBuffer; // rbx
  _QWORD *v18; // rax
  struct _SecBuffer *v19; // rsi
  unsigned int cbBuffer; // esi
  void *v21; // rax
  __int64 v22; // rax
  void *v23; // r15
  __int64 v24; // r14
  unsigned int v25; // esi
  unsigned int *v26; // rbx
  __int64 ppvContext; // r9
  DWORD v28; // r8d
  int v29; // eax
  __int64 v30; // r14
  unsigned int v31; // esi
  _DWORD *v32; // r12
  const CERT_CONTEXT *v33; // rbx
  HCERTSTORE v34; // r15
  const CERT_CONTEXT *v35; // rax
  DWORD LastError; // eax
  DWORD v37; // eax
  __int64 v38; // rcx
  HCERTSTORE v39; // rax
  int v40; // r12d
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // ebx
  void *v44; // rax
  unsigned int v45; // ecx
  HCERTSTORE hCertStore; // [rsp+48h] [rbp-89h]
  char v47; // [rsp+50h] [rbp-81h]
  int v48; // [rsp+54h] [rbp-7Dh]
  __int128 pvPara; // [rsp+58h] [rbp-79h] BYREF
  __int64 v50; // [rsp+68h] [rbp-69h]
  struct _SecBuffer v51; // [rsp+70h] [rbp-61h] BYREF
  _BYTE v52[4]; // [rsp+88h] [rbp-49h] BYREF
  unsigned int v53; // [rsp+8Ch] [rbp-45h]
  __int64 v54; // [rsp+90h] [rbp-41h]
  __int64 v55; // [rsp+98h] [rbp-39h]
  __int64 v56; // [rsp+A0h] [rbp-31h]
  unsigned int v57; // [rsp+B0h] [rbp-21h]
  __int64 v58; // [rsp+B8h] [rbp-19h]
  unsigned int v59; // [rsp+C0h] [rbp-11h]
  int v60; // [rsp+C4h] [rbp-Dh]
  struct _TLS_PARAMETERS *v61; // [rsp+C8h] [rbp-9h]
  __int64 v62; // [rsp+D0h] [rbp-1h]
  __int128 v63; // [rsp+D8h] [rbp+7h] BYREF
  __int64 v64; // [rsp+E8h] [rbp+17h]

  v4 = a2;
  v6 = 80;
  pvPara = 0;
  memset_0(v52, 0, 0x50u);
  v63 = 0;
  v64 = 0;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
  if ( !LsaTable )
    return 2148074333LL;
  if ( !(*(unsigned __int8 (__fastcall **)(__int128 *))(LsaTable + 192))(&v63) )
    return 2148074244LL;
  v9 = 0;
  v10 = BYTE8(v63) & 0x11;
  hCertStore = 0;
  v11 = *(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, void *))(LsaTable + 80);
  if ( v4 != 3 )
  {
    if ( v4 != 4 )
      v6 = 72;
    v12 = v11(0, v6, v52, a1);
    if ( v12 < 0 )
      goto LABEL_20;
LABEL_14:
    memset_0((char *)a4 + 4, 0, 0x6Cu);
    *(_DWORD *)a4 = v4;
    if ( (unsigned int)(v4 - 3) <= 1 )
    {
      v13 = v53;
      v15 = v54;
      v14 = v55;
      v47 = 1;
    }
    else
    {
      v13 = v54;
      v14 = v56;
      v47 = 0;
      v15 = v55;
    }
    v50 = v14;
    if ( v13 > 0x64 )
      goto LABEL_18;
    pvBuffer = (unsigned int *)a3->pvBuffer;
    if ( pvBuffer )
    {
      v19 = a3;
    }
    else
    {
      if ( (!v13 || !v15) && !v14 )
      {
        pvBuffer = 0;
        cbBuffer = 0;
LABEL_53:
        if ( v13 && v15 )
        {
          *((_DWORD *)a4 + 1) = v13;
          v21 = SPExternalAlloc(56 * v13);
          *((_QWORD *)a4 + 1) = v21;
          if ( !v21 )
          {
LABEL_18:
            v12 = -2146893056;
LABEL_19:
            v9 = hCertStore;
            goto LABEL_20;
          }
          hCertStore = CertOpenStore((LPCSTR)2, 0, 0, 4u, 0);
          v9 = hCertStore;
          if ( !hCertStore )
          {
            GetLastError();
            v12 = -2146893056;
            goto LABEL_20;
          }
          v22 = 0;
          v23 = hCertStore;
          while ( 1 )
          {
            v48 = v22;
            if ( (unsigned int)v22 >= v13 )
              break;
            if ( cbBuffer < 4 )
              goto LABEL_49;
            v24 = *pvBuffer;
            v25 = cbBuffer - 4;
            if ( v25 < (unsigned int)v24 )
              goto LABEL_49;
            v26 = pvBuffer + 1;
            if ( !v26 )
              goto LABEL_49;
            if ( (unsigned int)v24 < 0x18 )
              goto LABEL_49;
            ppvContext = *((_QWORD *)a4 + 1) + 56 * v22;
            *(_QWORD *)(ppvContext + 16) = *(_QWORD *)v26;
            *(_BYTE *)(ppvContext + 24) = v26[2] != 0;
            *(_QWORD *)(ppvContext + 32) = *(_QWORD *)(v26 + 3);
            v28 = v26[5];
            if ( (int)v24 - 24 < v28 )
              goto LABEL_49;
            if ( !CertAddSerializedElementToStore(
                    v23,
                    (const BYTE *)v26 + 24,
                    v28,
                    4u,
                    0,
                    2u,
                    0,
                    (const void **)ppvContext) )
              goto LABEL_93;
            v29 = HIDWORD(v58);
            pvBuffer = (unsigned int *)((char *)v26 + v24);
            cbBuffer = v25 - v24;
            if ( v47 )
              v29 = v62;
            if ( (v29 & 0x10000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
              }
              if ( cbBuffer < 4 )
                goto LABEL_49;
              v30 = *pvBuffer;
              v31 = cbBuffer - 4;
              if ( v31 < (unsigned int)v30 )
                goto LABEL_49;
              v32 = pvBuffer + 1;
              if ( pvBuffer == (unsigned int *)-4LL )
                goto LABEL_49;
              if ( (unsigned int)v30 < 4 )
                goto LABEL_49;
              LODWORD(pvPara) = *v32;
              *((_QWORD *)&pvPara + 1) = pvBuffer + 2;
              if ( v30 - 4 < (unsigned __int64)(unsigned int)pvPara )
                goto LABEL_49;
              v33 = 0;
              v34 = CertOpenStore((LPCSTR)6, 1u, 0, 0, &pvPara);
              if ( !v34 )
              {
LABEL_93:
                v12 = -2146893043;
                goto LABEL_19;
              }
              while ( 1 )
              {
                v35 = CertEnumCertificatesInStore(v34, v33);
                v33 = v35;
                if ( !v35 )
                  break;
                if ( !CertAddCertificateContextToStore(hCertStore, v35, 1u, 0) && GetLastError() != -2146885627 )
                {
                  if ( !CertCloseStore(v34, 2u)
                    && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    LastError = GetLastError();
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      14,
                      WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids,
                      LastError);
                  }
                  CertFreeCertificateContext(v33);
                  goto LABEL_92;
                }
              }
              pvBuffer = (_DWORD *)((char *)v32 + v30);
              cbBuffer = v31 - v30;
              if ( !CertCloseStore(v34, 2u)
                && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v37 = GetLastError();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, v37);
              }
              v23 = hCertStore;
            }
            v22 = (unsigned int)(v48 + 1);
          }
          v4 = a2;
        }
        if ( v50 )
        {
          if ( cbBuffer < 4 )
            goto LABEL_49;
          v38 = *pvBuffer;
          if ( cbBuffer - 4 < (unsigned int)v38 || pvBuffer == (unsigned int *)-4LL || (unsigned int)v38 < 4 )
            goto LABEL_49;
          LODWORD(pvPara) = pvBuffer[1];
          *((_QWORD *)&pvPara + 1) = pvBuffer + 2;
          if ( v38 - 4 < (unsigned __int64)(unsigned int)pvPara )
          {
            v12 = -2146893052;
            goto LABEL_19;
          }
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
          }
          v39 = CertOpenStore((LPCSTR)6, 1u, 0, 0, &pvPara);
          *((_QWORD *)a4 + 2) = v39;
          if ( !v39 )
          {
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
            }
LABEL_92:
            v12 = -2146893043;
            goto LABEL_19;
          }
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, v39);
          }
        }
        v40 = v4 - 4;
        if ( v40 )
        {
          if ( v40 != 1 )
          {
LABEL_126:
            v12 = 0;
            goto LABEL_19;
          }
          v12 = CopyTlsParameters(v61, v59, 0, 1u, (struct _TLS_PARAMETERS **)a4 + 13, (unsigned int *)a4 + 24);
          if ( v12 )
            goto LABEL_19;
          *(_QWORD *)((char *)a4 + 84) = v58;
          v41 = v53;
        }
        else
        {
          v42 = v57;
          if ( v57 && v58 )
          {
            if ( v57 > 0x100
              || (v43 = 4 * v57,
                  *((_DWORD *)a4 + 14) = v57,
                  v44 = SPExternalAlloc(4 * v42),
                  (*((_QWORD *)a4 + 8) = v44) == 0) )
            {
              v12 = -2146893056;
              goto LABEL_19;
            }
            v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, __int64))(LsaTable + 80))(0, v43, v44, v58);
            if ( v12 < 0 )
              goto LABEL_19;
          }
          v45 = v59;
          if ( v59 == -1 )
            v45 = 0;
          *((_DWORD *)a4 + 19) = v60;
          *((_QWORD *)a4 + 10) = v61;
          *((_DWORD *)a4 + 22) = v62;
          v41 = HIDWORD(v62);
          *((_DWORD *)a4 + 18) = v45 & 0x3FFFFFFF;
        }
        *((_DWORD *)a4 + 23) = v41;
        goto LABEL_126;
      }
      if ( !v10 )
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
        v12 = 590610;
        goto LABEL_19;
      }
      v51.cbBuffer = 8;
      v51.BufferType = 1;
      v18 = SPExternalAlloc(8u);
      v51.pvBuffer = v18;
      if ( !v18 )
        goto LABEL_18;
      v19 = a3;
      *v18 = a1;
      v12 = PerformApplicationCallback(0xAu, 0, 0, &v51, a3, 1, 0, 1);
      if ( v51.pvBuffer )
        SPExternalFree(v51.pvBuffer);
      if ( v12 < 0 )
        goto LABEL_19;
      pvBuffer = (unsigned int *)a3->pvBuffer;
      if ( !pvBuffer )
      {
LABEL_49:
        v12 = -2146893052;
        goto LABEL_19;
      }
    }
    cbBuffer = v19->cbBuffer;
    goto LABEL_53;
  }
  v12 = v11(0, 72, v52, a1);
  if ( v12 >= 0 )
  {
    v62 = 0;
    goto LABEL_14;
  }
LABEL_20:
  if ( a3 )
  {
    v16 = 0;
    if ( (BYTE8(v63) & 0x10) != 0 )
      v16 = a3->pvBuffer;
    CleanupAppModeInfo(0, a3);
    if ( v16 )
      SPExternalFree(v16);
  }
  if ( v9 )
    CertCloseStore(v9, 0);
  if ( v12 < 0 )
    FreeSchannelCred(a4, 1u);
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
    && ((*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && v12 || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0) )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids,
      (unsigned int)v12,
      v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002adf4  mov     rax, rsp
0x18002adf7  mov     [rax+8], rbx
0x18002adfb  mov     [rax+18h], r8
0x18002adff  mov     [rax+10h], edx
0x18002ae02  push    rbp
0x18002ae03  push    rsi
0x18002ae04  push    rdi
0x18002ae05  push    r12
0x18002ae07  push    r13
0x18002ae09  push    r14
0x18002ae0b  push    r15
0x18002ae0d  lea     rbp, [rax-5Fh]
0x18002ae11  sub     rsp, 0F0h
0x18002ae18  mov     r12d, edx
0x18002ae1b  mov     r15, rcx
0x18002ae1e  xorps   xmm0, xmm0
0x18002ae21  lea     rcx, [rbp+57h+var_A0]; void *
0x18002ae25  mov     ebx, 50h ; 'P'
0x18002ae2a  xor     edx, edx; Val
0x18002ae2c  mov     r8d, ebx; Size
0x18002ae2f  mov     rdi, r9
0x18002ae32  movups  [rbp+57h+var_D0], xmm0
0x18002ae36  call    memset_0
0x18002ae3b  xorps   xmm0, xmm0
0x18002ae3e  xor     eax, eax
0x18002ae40  movups  [rbp+57h+var_50], xmm0
0x18002ae44  mov     [rbp+57h+var_40], rax
0x18002ae48  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae4f  lea     r13, WPP_GLOBAL_Control
0x18002ae56  cmp     rcx, r13
0x18002ae59  jz      short loc_18002AE74
0x18002ae5b  test    byte ptr [rcx+1Ch], 20h
0x18002ae5f  jz      short loc_18002AE74
0x18002ae61  mov     rcx, [rcx+10h]
0x18002ae65  lea     edx, [rbx-46h]
0x18002ae68  lea     r8, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18002ae6f  call    WPP_SF_
0x18002ae74  mov     rax, cs:LsaTable
0x18002ae7b  test    rax, rax
0x18002ae7e  jnz     short loc_18002AE8A
0x18002ae80  mov     eax, 8009035Dh
0x18002ae85  jmp     loc_18002AFEE
0x18002ae8a  mov     rax, [rax+0C0h]
0x18002ae91  lea     rcx, [rbp+57h+var_50]
0x18002ae95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae9a  test    al, al
0x18002ae9c  jnz     short loc_18002AEA8
0x18002ae9e  mov     eax, 80090304h
0x18002aea3  jmp     loc_18002AFEE
0x18002aea8  mov     esi, dword ptr [rbp+57h+var_50+8]
0x18002aeab  lea     r8, [rbp+57h+var_A0]
0x18002aeaf  mov     rax, cs:LsaTable
0x18002aeb6  xor     r14d, r14d
0x18002aeb9  and     esi, 11h
0x18002aebc  mov     [rsp+120h+hCertStore], r14
0x18002aec1  mov     r9, r15
0x18002aec4  mov     rax, [rax+50h]
0x18002aec8  cmp     r12d, 3
0x18002aecc  jnz     short loc_18002AEE9
0x18002aece  lea     edx, [r14+48h]
0x18002aed2  xor     ecx, ecx
0x18002aed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aed9  mov     ebx, eax
0x18002aedb  test    eax, eax
0x18002aedd  js      loc_18002AF63
0x18002aee3  mov     [rbp+57h+var_58], r14
0x18002aee7  jmp     short loc_18002AF04
0x18002aee9  mov     ecx, 48h ; 'H'
0x18002aeee  cmp     r12d, 4
0x18002aef2  cmovnz  ebx, ecx
0x18002aef5  xor     ecx, ecx
0x18002aef7  mov     edx, ebx
0x18002aef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aefe  mov     ebx, eax
0x18002af00  test    eax, eax
0x18002af02  js      short loc_18002AF63
0x18002af04  xor     edx, edx; Val
0x18002af06  lea     rcx, [rdi+4]; void *
0x18002af0a  lea     r8d, [rdx+6Ch]; Size
0x18002af0e  call    memset_0
0x18002af13  lea     eax, [r12-3]
0x18002af18  mov     [rdi], r12d
0x18002af1b  cmp     eax, 1
0x18002af1e  jbe     short loc_18002AF33
0x18002af20  mov     r13d, dword ptr [rbp+57h+var_98]
0x18002af24  mov     rax, [rbp+57h+var_88]
0x18002af28  mov     [rsp+48h], r14b
0x18002af2d  mov     r14, [rbp+57h+var_90]
0x18002af31  jmp     short loc_18002AF44
0x18002af33  mov     r13d, [rbp+57h+var_9C]
0x18002af37  mov     r14, [rbp+57h+var_98]
0x18002af3b  mov     rax, [rbp+57h+var_90]
0x18002af3f  mov     byte ptr [rsp+48h], 1
0x18002af44  mov     [rbp+57h+var_C0], rax
0x18002af48  cmp     r13d, 64h ; 'd'
0x18002af4c  jbe     loc_18002B009
0x18002af52  mov     ebx, 80090300h
0x18002af57  lea     r13, WPP_GLOBAL_Control
0x18002af5e  mov     r14, [rsp+120h+hCertStore]
0x18002af63  mov     rcx, [rbp+57h+arg_10]
0x18002af67  test    rcx, rcx
0x18002af6a  jz      short loc_18002AF8F
0x18002af6c  xor     esi, esi
0x18002af6e  test    byte ptr [rbp+57h+var_50+8], 10h
0x18002af72  jz      short loc_18002AF78
0x18002af74  mov     rsi, [rcx+8]
0x18002af78  mov     rdx, rcx
0x18002af7b  xor     ecx, ecx
0x18002af7d  call    ?CleanupAppModeInfo@@YAXW4_UserDataCleanupAction@@PEAU_SecBuffer@@@Z; CleanupAppModeInfo(_UserDataCleanupAction,_SecBuffer *)
0x18002af82  test    rsi, rsi
0x18002af85  jz      short loc_18002AF8F
0x18002af87  mov     rcx, rsi; void *
0x18002af8a  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18002af8f  test    r14, r14
0x18002af92  jz      short loc_18002AF9F
0x18002af94  xor     edx, edx; dwFlags
0x18002af96  mov     rcx, r14; hCertStore
0x18002af99  call    cs:__imp_CertCloseStore
0x18002af9f  test    ebx, ebx
0x18002afa1  jns     short loc_18002AFAD
0x18002afa3  mov     dl, 1; unsigned __int8
0x18002afa5  mov     rcx, rdi; struct LSA_SCHANNEL_CRED *
0x18002afa8  call    ?FreeSchannelCred@@YAXPEAULSA_SCHANNEL_CRED@@E@Z; FreeSchannelCred(LSA_SCHANNEL_CRED *,uchar)
0x18002afad  mov     rax, cs:WPP_GLOBAL_Control
0x18002afb4  cmp     rax, r13
0x18002afb7  jz      short loc_18002AFEC
0x18002afb9  test    byte ptr [rax+1Ch], 1
0x18002afbd  jz      short loc_18002AFC3
0x18002afbf  test    ebx, ebx
0x18002afc1  jnz     short loc_18002AFC9
0x18002afc3  test    byte ptr [rax+1Ch], 4
0x18002afc7  jz      short loc_18002AFEC
0x18002afc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afd0  lea     r8, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18002afd7  mov     edx, 13h
0x18002afdc  mov     dword ptr [rsp+120h+pvPara], ebx
0x18002afe0  mov     r9d, ebx
0x18002afe3  mov     rcx, [rcx+10h]
0x18002afe7  call    WPP_SF_dd
0x18002afec  mov     eax, ebx
0x18002afee  mov     rbx, [rsp+120h+arg_0]
0x18002aff6  add     rsp, 0F0h
0x18002affd  pop     r15
0x18002afff  pop     r14
0x18002b001  pop     r13
0x18002b003  pop     r12
0x18002b005  pop     rdi
0x18002b006  pop     rsi
0x18002b007  pop     rbp
0x18002b008  retn
0x18002b009  mov     rbx, [rbp+57h+arg_10]
0x18002b00d  mov     rbx, [rbx+8]
0x18002b011  test    rbx, rbx
0x18002b014  jnz     loc_18002B0ED
0x18002b01a  test    r13d, r13d
0x18002b01d  jz      short loc_18002B024
0x18002b01f  test    r14, r14
0x18002b022  jnz     short loc_18002B02D
0x18002b024  test    rax, rax
0x18002b027  jz      loc_18002B0E7
0x18002b02d  test    esi, esi
0x18002b02f  jnz     short loc_18002B067
0x18002b031  mov     rax, cs:WPP_GLOBAL_Control
0x18002b038  lea     r13, WPP_GLOBAL_Control
0x18002b03f  cmp     rax, r13
0x18002b042  jz      short loc_18002B05D
0x18002b044  test    byte ptr [rax+1Ch], 4
0x18002b048  jz      short loc_18002B05D
0x18002b04a  mov     rcx, [rax+10h]
0x18002b04e  lea     edx, [rsi+0Ch]
0x18002b051  lea     r8, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18002b058  call    WPP_SF_
0x18002b05d  mov     ebx, 90312h
0x18002b062  jmp     loc_18002AF5E
0x18002b067  mov     ecx, 8; uBytes
0x18002b06c  mov     [rbp+57h+var_B8.pvBuffer], 0
0x18002b074  mov     [rbp+57h+var_B8.cbBuffer], ecx
0x18002b077  lea     ebx, [rcx-7]
0x18002b07a  mov     [rbp+57h+var_B8.BufferType], ebx
0x18002b07d  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18002b082  mov     [rbp+57h+var_B8.pvBuffer], rax
0x18002b086  test    rax, rax
0x18002b089  jz      loc_18002AF52
0x18002b08f  mov     rsi, [rbp+57h+arg_10]
0x18002b093  lea     r9, [rbp+57h+var_B8]; struct _SecBuffer *
0x18002b097  mov     byte ptr [rsp+120h+ppvContext], bl; char
0x18002b09b  lea     ecx, [rbx+9]; unsigned int
0x18002b09e  mov     dword ptr [rsp+120h+pdwContextType], 0; int
0x18002b0a6  xor     r8d, r8d; unsigned __int64
0x18002b0a9  mov     [rsp+120h+dwContextTypeFlags], ebx; int
0x18002b0ad  xor     edx, edx; unsigned __int64
0x18002b0af  mov     [rsp+120h+pvPara], rsi; struct _SecBuffer *
0x18002b0b4  mov     [rax], r15
0x18002b0b7  call    ?PerformApplicationCallback@@YAJK_K0PEAU_SecBuffer@@1HHE@Z; PerformApplicationCallback(ulong,unsigned __int64,unsigned __int64,_SecBuffer *,_SecBuffer *,int,int,uchar)
0x18002b0bc  mov     rcx, [rbp+57h+var_B8.pvBuffer]; void *
0x18002b0c0  mov     ebx, eax
0x18002b0c2  test    rcx, rcx
0x18002b0c5  jz      short loc_18002B0CC
0x18002b0c7  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18002b0cc  test    ebx, ebx
0x18002b0ce  js      loc_18002AF57
0x18002b0d4  mov     rbx, [rsi+8]
0x18002b0d8  test    rbx, rbx
0x18002b0db  jnz     short loc_18002B0F1
0x18002b0dd  mov     ebx, 80090304h
0x18002b0e2  jmp     loc_18002AF57
0x18002b0e7  xor     ebx, ebx
0x18002b0e9  xor     esi, esi
0x18002b0eb  jmp     short loc_18002B0F3
0x18002b0ed  mov     rsi, [rbp+57h+arg_10]
0x18002b0f1  mov     esi, [rsi]
0x18002b0f3  test    r13d, r13d
0x18002b0f6  jz      loc_18002B3E9
0x18002b0fc  test    r14, r14
0x18002b0ff  jz      loc_18002B3E9
0x18002b105  imul    ecx, r13d, 38h ; '8'; uBytes
0x18002b109  mov     [rdi+4], r13d
0x18002b10d  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18002b112  mov     [rdi+8], rax
0x18002b116  test    rax, rax
0x18002b119  jz      loc_18002AF52
0x18002b11f  xor     edx, edx; dwEncodingType
0x18002b121  mov     [rsp+120h+pvPara], 0; pvPara
0x18002b12a  mov     r9d, 4; dwFlags
0x18002b130  xor     r8d, r8d; hCryptProv
0x18002b133  lea     ecx, [rdx+2]; lpszStoreProvider
0x18002b136  call    cs:__imp_CertOpenStore
0x18002b13c  mov     [rsp+120h+hCertStore], rax
0x18002b141  mov     r14, rax
0x18002b144  test    rax, rax
0x18002b147  jnz     short loc_18002B160
0x18002b149  call    cs:__imp_GetLastError
0x18002b14f  mov     ebx, 80090300h
0x18002b154  lea     r13, WPP_GLOBAL_Control
0x18002b15b  jmp     loc_18002AF63
0x18002b160  xor     eax, eax
0x18002b162  mov     r15, r14
0x18002b165  mov     [rbp+57h+var_D4], eax
0x18002b168  cmp     eax, r13d
0x18002b16b  jnb     loc_18002B3E5
0x18002b171  cmp     esi, 4
0x18002b174  jb      loc_18002B0DD
0x18002b17a  mov     r14d, [rbx]
0x18002b17d  add     esi, 0FFFFFFFCh
0x18002b180  cmp     esi, r14d
0x18002b183  jb      loc_18002B0DD
0x18002b189  add     rbx, 4
0x18002b18d  jz      loc_18002B0DD
0x18002b193  cmp     r14d, 18h
0x18002b197  jb      loc_18002B0DD
0x18002b19d  imul    r9, rax, 38h ; '8'
0x18002b1a1  mov     rax, [rbx]
0x18002b1a4  xor     ecx, ecx
0x18002b1a6  add     r9, [rdi+8]
0x18002b1aa  mov     [r9+10h], rax
0x18002b1ae  cmp     [rbx+8], ecx
0x18002b1b1  setnz   al
0x18002b1b4  mov     [r9+18h], al
0x18002b1b8  mov     rax, [rbx+0Ch]
0x18002b1bc  mov     [r9+20h], rax
0x18002b1c0  lea     eax, [r14-18h]
0x18002b1c4  mov     r8d, [rbx+14h]; cbElement
0x18002b1c8  cmp     eax, r8d
0x18002b1cb  jb      loc_18002B0DD
0x18002b1d1  mov     [rsp+120h+ppvContext], r9; ppvContext
0x18002b1d6  lea     rdx, [rbx+18h]; pbElement
0x18002b1da  mov     [rsp+120h+pdwContextType], rcx; pdwContextType
0x18002b1df  lea     r9d, [rcx+4]; dwAddDisposition
0x18002b1e3  mov     [rsp+120h+dwContextTypeFlags], 2; dwContextTypeFlags
0x18002b1eb  mov     dword ptr [rsp+120h+pvPara], ecx; dwFlags
0x18002b1ef  mov     rcx, r15; hCertStore
0x18002b1f2  call    cs:__imp_CertAddSerializedElementToStore
0x18002b1f8  test    eax, eax
0x18002b1fa  jz      loc_18002B3DB
0x18002b200  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18002b203  add     rbx, r14
0x18002b206  sub     esi, r14d
0x18002b209  cmp     byte ptr [rsp+48h], 0
0x18002b20e  cmovnz  eax, dword ptr [rbp+57h+var_58]
0x18002b212  bt      eax, 10h
0x18002b216  jnb     loc_18002B3B7
0x18002b21c  mov     rax, cs:WPP_GLOBAL_Control
0x18002b223  lea     rcx, WPP_GLOBAL_Control
0x18002b22a  cmp     rax, rcx
0x18002b22d  jz      short loc_18002B24A
0x18002b22f  test    byte ptr [rax+1Ch], 4
0x18002b233  jz      short loc_18002B24A
0x18002b235  mov     rcx, [rax+10h]
0x18002b239  lea     r8, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18002b240  mov     edx, 0Dh
0x18002b245  call    WPP_SF_
0x18002b24a  cmp     esi, 4
0x18002b24d  jb      loc_18002B0DD
0x18002b253  mov     r14d, [rbx]
0x18002b256  add     esi, 0FFFFFFFCh
0x18002b259  cmp     esi, r14d
0x18002b25c  jb      loc_18002B0DD
0x18002b262  lea     r12, [rbx+4]
0x18002b266  test    r12, r12
0x18002b269  jz      loc_18002B0DD
  ... truncated ...
```
