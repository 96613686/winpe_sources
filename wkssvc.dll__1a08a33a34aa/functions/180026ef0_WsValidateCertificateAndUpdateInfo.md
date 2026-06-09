# WsValidateCertificateAndUpdateInfo

- ea: `0x180026ef0`
- end: `0x180027563`
- name: `WsValidateCertificateAndUpdateInfo`
- size: `1651`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180022510`
- `0x180023930`

## callees

- `0x180022a24`
- `0x180024494`
- `0x180024520`
- `0x180024550`
- `0x180025e78`
- `0x180026948`
- `0x180026ae8`
- `0x180026ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002713c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002737e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002713c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002737e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027511`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800271a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027202`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027277`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800271a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027202`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027277`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002734b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800274d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002734b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800274d4`
- `CRYPT32!CertOpenStore` at `0x180026f78`
- `CRYPT32!CertOpenStore` at `0x180026f78`
- `CRYPT32!CertFindCertificateInStore` at `0x18002703e`
- `CRYPT32!CertFindCertificateInStore` at `0x18002703e`
- `CRYPT32!CertCloseStore` at `0x18002736e`
- `CRYPT32!CertCloseStore` at `0x180027501`
- `CRYPT32!CertCloseStore` at `0x18002736e`
- `CRYPT32!CertCloseStore` at `0x180027501`
- `CRYPT32!CertFreeCertificateContext` at `0x18002735a`
- `CRYPT32!CertFreeCertificateContext` at `0x1800274e8`
- `CRYPT32!CertFreeCertificateContext` at `0x18002735a`
- `CRYPT32!CertFreeCertificateContext` at `0x1800274e8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800272e9`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800272e9`

## pseudocode

```c
__int64 __fastcall WsValidateCertificateAndUpdateInfo(__int64 **a1, __int64 a2)
{
  __int64 *v2; // rax
  const CERT_CONTEXT *v4; // rbp
  char v5; // r12
  char v6; // r13
  __int64 v7; // rcx
  char v8; // r15
  HCERTSTORE v9; // r14
  DWORD LastError; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  PCCERT_CONTEXT CertificateInStore; // rax
  __int64 v19; // r8
  _QWORD *v20; // rcx
  _QWORD *v21; // rcx
  _QWORD *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rax
  SIZE_T v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rcx
  DWORD v30; // eax
  __int64 v32; // rbx
  DWORD v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  DWORD v39; // eax
  int pvData; // [rsp+30h] [rbp-68h] BYREF
  _OWORD pvFindPara[6]; // [rsp+38h] [rbp-60h] BYREF
  char v42; // [rsp+A0h] [rbp+8h]
  char v43; // [rsp+A8h] [rbp+10h]
  char v44; // [rsp+B0h] [rbp+18h]
  DWORD pcbData; // [rsp+B8h] [rbp+20h] BYREF

  pcbData = 4;
  pvData = 0;
  pvFindPara[0] = 0;
  v2 = *a1;
  v4 = 0;
  v42 = 0;
  v5 = 0;
  v43 = 0;
  v44 = 0;
  v6 = 0;
  v7 = **a1;
  v8 = 0;
  if ( !*(_QWORD *)*v2 || !*(_QWORD *)(v7 + 24) || !*(_QWORD *)(v7 + 64) )
  {
    v9 = 0;
    v11 = 87;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_73;
    }
    v16 = 77;
    v17 = 87;
LABEL_72:
    WPP_SF_d(v15[2], v16, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, v17);
    goto LABEL_73;
  }
  v9 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x28000u, *(const void **)(v7 + 64));
  if ( !v9 )
  {
    LastError = GetLastError();
    v11 = LastError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v13 = 78;
LABEL_35:
      WPP_SF_d(v12[2], v13, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, LastError);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  v14 = LmConvertCryptStringToBinary(*(LPCWSTR *)(**a1 + 24), (DWORD *)pvFindPara);
  v11 = v14;
  if ( v14 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_73;
    }
    v16 = 79;
    v17 = v14;
    goto LABEL_72;
  }
  CertificateInStore = CertFindCertificateInStore(v9, 0x10001u, 0, 0x10000u, pvFindPara, 0);
  v4 = CertificateInStore;
  if ( !CertificateInStore )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v32 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v33 = GetLastError();
      WPP_SF_d(v32, 84, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, v33);
    }
    v11 = 1168;
    goto LABEL_73;
  }
  v20 = (_QWORD *)(**a1 + 8);
  if ( *v20 )
  {
LABEL_22:
    v21 = (_QWORD *)(**a1 + 16);
    if ( !*v21 )
    {
      if ( !(unsigned int)WsGetCertificateName(v21, 4, 1, v4) )
      {
        LastError = GetLastError();
        v11 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v13 = 81;
          goto LABEL_35;
        }
        goto LABEL_36;
      }
      v5 = 1;
    }
    v22 = (_QWORD *)(**a1 + 32);
    if ( !*v22 )
    {
      if ( !(unsigned int)WsGetOptionalCertificateName(v22, 5, v19, v4) )
      {
        LastError = GetLastError();
        v11 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v13 = 82;
          goto LABEL_35;
        }
        goto LABEL_36;
      }
      v6 = 1;
    }
    if ( !*(_QWORD *)(**a1 + 40) )
    {
      *(_QWORD *)(**a1 + 40) = LocalAlloc(0x40u, 0x2Au);
      v23 = *(_QWORD *)(**a1 + 40);
      if ( !v23 )
        return 0;
      RtlStringCbPrintfW(v23, 42, L"%llu", *(_QWORD *)&v4->pCertInfo->NotBefore);
      v43 = 1;
    }
    if ( *(_QWORD *)(**a1 + 48) )
    {
LABEL_45:
      v25 = **a1;
      if ( !*(_QWORD *)(v25 + 56) )
      {
        v26 = -1;
        do
          ++v26;
        while ( *(_WORD *)(*(_QWORD *)(v25 + 64) + 2 * v26) );
        v27 = 2 * v26 + 40;
        *(_QWORD *)(**a1 + 56) = LocalAlloc(0x40u, v27);
        v28 = **a1;
        v29 = *(_QWORD *)(v28 + 56);
        if ( !v29 )
          return 0;
        RtlStringCbPrintfW(v29, v27, L"%ws%ws", L"cert:\\LocalMachine\\", *(_QWORD *)(v28 + 64));
        v8 = 1;
      }
      *(_DWORD *)(**a1 + 80) = 0;
      *(_DWORD *)(**a1 + 88) = 0;
      if ( CertGetCertificateContextProperty(v4, 6u, &pvData, &pcbData) )
      {
        if ( *((_QWORD *)&pvFindPara[0] + 1) )
          LocalFree(*((HLOCAL *)&pvFindPara[0] + 1));
        CertFreeCertificateContext(v4);
        if ( !CertCloseStore(v9, 2u) )
        {
          v30 = GetLastError();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, v30);
          }
        }
        return 0;
      }
      v11 = -1067646970;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids);
      }
      goto LABEL_73;
    }
    *(_QWORD *)(**a1 + 48) = LocalAlloc(0x40u, 0x2Au);
    v24 = *(_QWORD *)(**a1 + 48);
    if ( v24 )
    {
      RtlStringCbPrintfW(v24, 42, L"%llu", *(_QWORD *)&v4->pCertInfo->NotAfter);
      v44 = 1;
      goto LABEL_45;
    }
    return 0;
  }
  if ( (unsigned int)WsGetOptionalCertificateName(v20, 2, v19, CertificateInStore) )
  {
    v42 = 1;
    goto LABEL_22;
  }
  LastError = GetLastError();
  v11 = LastError;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v13 = 80;
    goto LABEL_35;
  }
LABEL_36:
  if ( !v11 )
    return 0;
LABEL_73:
  LOBYTE(a2) = v42;
  WsFreeCertificateMappingField(**a1 + 8, a2);
  LOBYTE(v34) = v5;
  WsFreeCertificateMappingField(**a1 + 16, v34);
  LOBYTE(v35) = v6;
  WsFreeCertificateMappingField(**a1 + 32, v35);
  LOBYTE(v36) = v43;
  WsFreeCertificateMappingField(**a1 + 40, v36);
  LOBYTE(v37) = v44;
  WsFreeCertificateMappingField(**a1 + 48, v37);
  LOBYTE(v38) = v8;
  WsFreeCertificateMappingField(**a1 + 56, v38);
  if ( *((_QWORD *)&pvFindPara[0] + 1) )
    LocalFree(*((HLOCAL *)&pvFindPara[0] + 1));
  if ( v4 )
    CertFreeCertificateContext(v4);
  if ( v9 )
  {
    if ( !CertCloseStore(v9, 2u) )
    {
      v39 = GetLastError();
      v11 = v39;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, v39);
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180026ef0  mov     rax, rsp
0x180026ef3  push    rbx
0x180026ef4  push    rbp
0x180026ef5  push    rsi
0x180026ef6  push    rdi
0x180026ef7  push    r12
0x180026ef9  push    r13
0x180026efb  push    r14
0x180026efd  push    r15
0x180026eff  sub     rsp, 58h
0x180026f03  xor     edi, edi
0x180026f05  mov     dword ptr [rax+20h], 4
0x180026f0c  mov     [rax-68h], edi
0x180026f0f  xorps   xmm0, xmm0
0x180026f12  movups  xmmword ptr [rax-60h], xmm0
0x180026f16  mov     rax, [rcx]
0x180026f19  mov     rsi, rcx
0x180026f1c  mov     ebp, edi
0x180026f1e  mov     [rsp+98h+arg_0], dil
0x180026f26  mov     r12b, dil
0x180026f29  mov     [rsp+98h+arg_8], dil
0x180026f31  mov     [rsp+98h+arg_10], dil
0x180026f39  mov     r13b, dil
0x180026f3c  mov     rcx, [rax]
0x180026f3f  mov     r15b, dil
0x180026f42  cmp     [rcx], rdi
0x180026f45  jz      loc_180027415
0x180026f4b  cmp     [rcx+18h], rdi
0x180026f4f  jz      loc_180027415
0x180026f55  mov     rax, [rcx+40h]
0x180026f59  test    rax, rax
0x180026f5c  jz      loc_180027415
0x180026f62  mov     r9d, 28000h; dwFlags
0x180026f68  mov     [rsp+98h+pvPara], rax; pvPara
0x180026f6d  xor     r8d, r8d; hCryptProv
0x180026f70  lea     ecx, [rdi+0Ah]; lpszStoreProvider
0x180026f73  mov     edx, 10001h; dwEncodingType
0x180026f78  call    cs:__imp_CertOpenStore
0x180026f7f  nop     dword ptr [rax+rax+00h]
0x180026f84  mov     r14, rax
0x180026f87  test    rax, rax
0x180026f8a  jnz     short loc_180026FCD
0x180026f8c  call    cs:__imp_GetLastError
0x180026f93  nop     dword ptr [rax+rax+00h]
0x180026f98  mov     ebx, eax
0x180026f9a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180026fa1  lea     rdi, WPP_GLOBAL_Control
0x180026fa8  cmp     rcx, rdi
0x180026fab  jz      loc_180027181
0x180026fb1  test    byte ptr [rcx+1Ch], 2
0x180026fb5  jz      loc_180027181
0x180026fbb  cmp     byte ptr [rcx+19h], 1
0x180026fbf  jb      loc_180027181
0x180026fc5  lea     edx, [rbp+4Eh]
0x180026fc8  jmp     loc_18002716E
0x180026fcd  mov     rax, [rsi]
0x180026fd0  lea     rdx, [rsp+98h+pvFindPara]; pcbBinary
0x180026fd5  mov     rcx, [rax]
0x180026fd8  mov     rcx, [rcx+18h]; pszString
0x180026fdc  call    LmConvertCryptStringToBinary
0x180026fe1  mov     ebx, eax
0x180026fe3  test    eax, eax
0x180026fe5  jz      short loc_18002701F
0x180026fe7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180026fee  lea     rdi, WPP_GLOBAL_Control
0x180026ff5  cmp     rcx, rdi
0x180026ff8  jz      loc_180027452
0x180026ffe  test    byte ptr [rcx+1Ch], 2
0x180027002  jz      loc_180027452
0x180027008  cmp     byte ptr [rcx+19h], 1
0x18002700c  jb      loc_180027452
0x180027012  mov     edx, 4Fh ; 'O'
0x180027017  mov     r9d, eax
0x18002701a  jmp     loc_180027442
0x18002701f  mov     r9d, 10000h; dwFindType
0x180027025  mov     [rsp+98h+pPrevCertContext], rdi; pPrevCertContext
0x18002702a  lea     rax, [rsp+98h+pvFindPara]
0x18002702f  xor     r8d, r8d; dwFindFlags
0x180027032  mov     rcx, r14; hCertStore
0x180027035  mov     [rsp+98h+pvPara], rax; pvFindPara
0x18002703a  lea     edx, [r9+1]; dwCertEncodingType
0x18002703e  call    cs:__imp_CertFindCertificateInStore
0x180027045  nop     dword ptr [rax+rax+00h]
0x18002704a  mov     rbp, rax
0x18002704d  test    rax, rax
0x180027050  jz      loc_1800273C8
0x180027056  mov     rcx, [rsi]
0x180027059  mov     rcx, [rcx]
0x18002705c  add     rcx, 8
0x180027060  cmp     [rcx], rdi
0x180027063  jnz     short loc_1800270C1
0x180027065  mov     r9, rax
0x180027068  mov     edx, 2
0x18002706d  call    WsGetOptionalCertificateName
0x180027072  test    eax, eax
0x180027074  jnz     short loc_1800270B9
0x180027076  call    cs:__imp_GetLastError
0x18002707d  nop     dword ptr [rax+rax+00h]
0x180027082  mov     ebx, eax
0x180027084  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002708b  lea     rdi, WPP_GLOBAL_Control
0x180027092  cmp     rcx, rdi
0x180027095  jz      loc_180027181
0x18002709b  test    byte ptr [rcx+1Ch], 2
0x18002709f  jz      loc_180027181
0x1800270a5  cmp     byte ptr [rcx+19h], 1
0x1800270a9  jb      loc_180027181
0x1800270af  mov     edx, 50h ; 'P'
0x1800270b4  jmp     loc_18002716E
0x1800270b9  mov     [rsp+98h+arg_0], 1
0x1800270c1  mov     rax, [rsi]
0x1800270c4  mov     rcx, [rax]
0x1800270c7  add     rcx, 10h
0x1800270cb  cmp     [rcx], rdi
0x1800270ce  jnz     short loc_18002711C
0x1800270d0  mov     edx, 4
0x1800270d5  mov     r9, rbp
0x1800270d8  lea     r8d, [rdx-3]
0x1800270dc  call    WsGetCertificateName
0x1800270e1  test    eax, eax
0x1800270e3  jnz     short loc_180027119
0x1800270e5  call    cs:__imp_GetLastError
0x1800270ec  nop     dword ptr [rax+rax+00h]
0x1800270f1  mov     ebx, eax
0x1800270f3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800270fa  lea     rdi, WPP_GLOBAL_Control
0x180027101  cmp     rcx, rdi
0x180027104  jz      short loc_180027181
0x180027106  test    byte ptr [rcx+1Ch], 2
0x18002710a  jz      short loc_180027181
0x18002710c  cmp     byte ptr [rcx+19h], 1
0x180027110  jb      short loc_180027181
0x180027112  mov     edx, 51h ; 'Q'
0x180027117  jmp     short loc_18002716E
0x180027119  mov     r12b, 1
0x18002711c  mov     rax, [rsi]
0x18002711f  mov     rcx, [rax]
0x180027122  add     rcx, 20h ; ' '
0x180027126  cmp     [rcx], rdi
0x180027129  jnz     short loc_180027191
0x18002712b  mov     r9, rbp
0x18002712e  mov     edx, 5
0x180027133  call    WsGetOptionalCertificateName
0x180027138  test    eax, eax
0x18002713a  jnz     short loc_18002718E
0x18002713c  call    cs:__imp_GetLastError
0x180027143  nop     dword ptr [rax+rax+00h]
0x180027148  mov     ebx, eax
0x18002714a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180027151  lea     rdi, WPP_GLOBAL_Control
0x180027158  cmp     rcx, rdi
0x18002715b  jz      short loc_180027181
0x18002715d  test    byte ptr [rcx+1Ch], 2
0x180027161  jz      short loc_180027181
0x180027163  cmp     byte ptr [rcx+19h], 1
0x180027167  jb      short loc_180027181
0x180027169  mov     edx, 52h ; 'R'
0x18002716e  mov     rcx, [rcx+10h]
0x180027172  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180027179  mov     r9d, eax
0x18002717c  call    WPP_SF_d
0x180027181  test    ebx, ebx
0x180027183  jnz     loc_180027452
0x180027189  jmp     loc_1800273C1
0x18002718e  mov     r13b, 1
0x180027191  mov     rax, [rsi]
0x180027194  mov     ebx, 2Ah ; '*'
0x180027199  mov     rcx, [rax]
0x18002719c  cmp     [rcx+28h], rdi
0x1800271a0  jnz     short loc_1800271EE
0x1800271a2  mov     edx, ebx; uBytes
0x1800271a4  lea     ecx, [rbx+16h]; uFlags
0x1800271a7  call    cs:__imp_LocalAlloc
0x1800271ae  nop     dword ptr [rax+rax+00h]
0x1800271b3  mov     rcx, [rsi]
0x1800271b6  mov     rdx, [rcx]
0x1800271b9  mov     [rdx+28h], rax
0x1800271bd  mov     rax, [rsi]
0x1800271c0  mov     rcx, [rax]
0x1800271c3  mov     rcx, [rcx+28h]
0x1800271c7  test    rcx, rcx
0x1800271ca  jz      loc_1800273C1
0x1800271d0  mov     r9, [rbp+18h]
0x1800271d4  lea     r8, aLlu; "%llu"
0x1800271db  mov     edx, ebx
0x1800271dd  mov     r9, [r9+40h]
0x1800271e1  call    RtlStringCbPrintfW
0x1800271e6  mov     [rsp+98h+arg_8], 1
0x1800271ee  mov     rax, [rsi]
0x1800271f1  mov     rcx, [rax]
0x1800271f4  cmp     [rcx+30h], rdi
0x1800271f8  jnz     short loc_18002724A
0x1800271fa  mov     rdx, rbx; uBytes
0x1800271fd  mov     ecx, 40h ; '@'; uFlags
0x180027202  call    cs:__imp_LocalAlloc
0x180027209  nop     dword ptr [rax+rax+00h]
0x18002720e  mov     rcx, [rsi]
0x180027211  mov     rdx, [rcx]
0x180027214  mov     [rdx+30h], rax
0x180027218  mov     rax, [rsi]
0x18002721b  mov     rcx, [rax]
0x18002721e  mov     rcx, [rcx+30h]
0x180027222  test    rcx, rcx
0x180027225  jz      loc_1800273C1
0x18002722b  mov     r9, [rbp+18h]
0x18002722f  lea     r8, aLlu; "%llu"
0x180027236  mov     rdx, rbx
0x180027239  mov     r9, [r9+48h]
0x18002723d  call    RtlStringCbPrintfW
0x180027242  mov     [rsp+98h+arg_10], 1
0x18002724a  mov     rax, [rsi]
0x18002724d  mov     rcx, [rax]
0x180027250  cmp     [rcx+38h], rdi
0x180027254  jnz     short loc_1800272C2
0x180027256  mov     rdx, [rcx+40h]
0x18002725a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002725e  inc     rax
0x180027261  cmp     [rdx+rax*2], di
0x180027265  jnz     short loc_18002725E
0x180027267  lea     rbx, ds:28h[rax*2]
0x18002726f  mov     ecx, 40h ; '@'; uFlags
0x180027274  mov     rdx, rbx; uBytes
0x180027277  call    cs:__imp_LocalAlloc
0x18002727e  nop     dword ptr [rax+rax+00h]
0x180027283  mov     rcx, [rsi]
0x180027286  mov     rdx, [rcx]
0x180027289  mov     [rdx+38h], rax
0x18002728d  mov     rax, [rsi]
0x180027290  mov     rax, [rax]
0x180027293  mov     rcx, [rax+38h]
0x180027297  test    rcx, rcx
0x18002729a  jz      loc_1800273C1
0x1800272a0  mov     rax, [rax+40h]
0x1800272a4  lea     r9, aCertLocalmachi; "cert:\\LocalMachine\\"
0x1800272ab  lea     r8, aWsWs_0; "%ws%ws"
0x1800272b2  mov     [rsp+98h+pvPara], rax
0x1800272b7  mov     rdx, rbx
0x1800272ba  call    RtlStringCbPrintfW
0x1800272bf  mov     r15b, 1
0x1800272c2  mov     rax, [rsi]
0x1800272c5  lea     r9, [rsp+98h+pcbData]; pcbData
0x1800272cd  lea     r8, [rsp+98h+pvData]; pvData
0x1800272d2  mov     edx, 6; dwPropId
0x1800272d7  mov     rcx, [rax]
0x1800272da  mov     [rcx+50h], edi
0x1800272dd  mov     rax, [rsi]
0x1800272e0  mov     rcx, [rax]
0x1800272e3  mov     [rcx+58h], edi
0x1800272e6  mov     rcx, rbp; pCertContext
0x1800272e9  call    cs:__imp_CertGetCertificateContextProperty
0x1800272f0  nop     dword ptr [rax+rax+00h]
0x1800272f5  test    eax, eax
0x1800272f7  jnz     short loc_180027341
0x1800272f9  mov     ebx, 0C05D0006h
0x1800272fe  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180027305  lea     rdi, WPP_GLOBAL_Control
0x18002730c  cmp     rcx, rdi
0x18002730f  jz      loc_180027452
0x180027315  test    byte ptr [rcx+1Ch], 2
0x180027319  jz      loc_180027452
0x18002731f  cmp     byte ptr [rcx+19h], 1
0x180027323  jb      loc_180027452
0x180027329  mov     rcx, [rcx+10h]
0x18002732d  lea     edx, [rax+53h]
0x180027330  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180027337  call    WPP_SF_
0x18002733c  jmp     loc_180027452
0x180027341  mov     rcx, [rsp+98h+hMem]; hMem
0x180027346  test    rcx, rcx
0x180027349  jz      short loc_180027357
0x18002734b  call    cs:__imp_LocalFree
0x180027352  nop     dword ptr [rax+rax+00h]
0x180027357  mov     rcx, rbp; pCertContext
0x18002735a  call    cs:__imp_CertFreeCertificateContext
0x180027361  nop     dword ptr [rax+rax+00h]
0x180027366  mov     edx, 2; dwFlags
0x18002736b  mov     rcx, r14; hCertStore
0x18002736e  call    cs:__imp_CertCloseStore
0x180027375  nop     dword ptr [rax+rax+00h]
0x18002737a  test    eax, eax
0x18002737c  jnz     short loc_1800273C1
0x18002737e  call    cs:__imp_GetLastError
0x180027385  nop     dword ptr [rax+rax+00h]
0x18002738a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180027391  lea     rdi, WPP_GLOBAL_Control
0x180027398  cmp     rcx, rdi
0x18002739b  jz      short loc_1800273C1
0x18002739d  test    byte ptr [rcx+1Ch], 2
0x1800273a1  jz      short loc_1800273C1
0x1800273a3  cmp     byte ptr [rcx+19h], 1
0x1800273a7  jb      short loc_1800273C1
0x1800273a9  mov     rcx, [rcx+10h]
0x1800273ad  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x1800273b4  mov     edx, 55h ; 'U'
0x1800273b9  mov     r9d, eax
0x1800273bc  call    WPP_SF_d
0x1800273c1  xor     eax, eax
0x1800273c3  jmp     loc_180027551
0x1800273c8  mov     rbx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800273cf  lea     rdi, WPP_GLOBAL_Control
  ... truncated ...
```
