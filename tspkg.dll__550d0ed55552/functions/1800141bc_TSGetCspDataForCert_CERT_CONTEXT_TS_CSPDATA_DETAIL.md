# TSGetCspDataForCert(_CERT_CONTEXT *,_TS_CSPDATA_DETAIL *)

- ea: `0x1800141bc`
- end: `0x180014345`
- name: `?TSGetCspDataForCert@@YAJPEAU_CERT_CONTEXT@@PEAU_TS_CSPDATA_DETAIL@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCert, struct _TS_CSPDATA_DETAIL *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001449c`

## callees

- `0x1800032c0`
- `0x180005ed0`
- `0x1800133c4`
- `0x1800141bc`

## import_xrefs

- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x1800142d2`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x1800142d2`
- `ntdll!RtlFreeUnicodeString` at `0x18001432a`
- `ntdll!RtlFreeUnicodeString` at `0x18001432a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001420a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180014249`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001420a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180014249`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180014273`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180014273`
- `CRYPTSP!CryptReleaseContext` at `0x180014311`
- `CRYPTSP!CryptReleaseContext` at `0x180014311`
- `CRYPTSP!CryptGetProvParam` at `0x180014292`
- `CRYPTSP!CryptGetProvParam` at `0x1800142c1`
- `CRYPTSP!CryptGetProvParam` at `0x180014292`
- `CRYPTSP!CryptGetProvParam` at `0x1800142c1`

## pseudocode

```c
__int64 __fastcall TSGetCspDataForCert(PCCERT_CONTEXT pCert, struct _TS_CSPDATA_DETAIL *a2)
{
  char *v2; // rsi
  void *v5; // rdi
  unsigned int v6; // ebx
  void *v7; // rax
  BYTE *v8; // rax
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+30h] [rbp-20h] BYREF
  DWORD pdwKeySpec; // [rsp+34h] [rbp-1Ch] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+38h] [rbp-18h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+30h] BYREF
  DWORD pdwDataLen; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  pcbData = 0;
  phCryptProvOrNCryptKey = 0;
  pdwKeySpec = 8;
  pfCallerFreeProvOrNCryptKey = 0;
  pdwDataLen = 0;
  Destination = 0;
  if ( !CertGetCertificateContextProperty(pCert, 2u, 0, &pcbData) )
  {
    v5 = 0;
LABEL_3:
    v6 = -1073741023;
    goto LABEL_13;
  }
  v7 = TSAllocate(pcbData);
  v5 = v7;
  if ( !v7 )
  {
    v6 = -1073741670;
    goto LABEL_13;
  }
  if ( !CertGetCertificateContextProperty(pCert, 2u, v7, &pcbData)
    || !CryptAcquireCertificatePrivateKey(
          pCert,
          0x40u,
          0,
          &phCryptProvOrNCryptKey,
          &pdwKeySpec,
          &pfCallerFreeProvOrNCryptKey) )
  {
    goto LABEL_3;
  }
  if ( CryptGetProvParam(phCryptProvOrNCryptKey, 0x2Bu, 0, &pdwDataLen, 0) )
  {
    v8 = (BYTE *)TSAllocate(pdwDataLen);
    v2 = (char *)v8;
    if ( v8 )
    {
      if ( CryptGetProvParam(phCryptProvOrNCryptKey, 0x2Bu, v8, &pdwDataLen, 0) )
        RtlCreateUnicodeStringFromAsciiz(&Destination, v2);
    }
  }
  v6 = TSBuildCspDetail(
         0,
         Destination.Buffer,
         *(unsigned __int16 **)v5,
         *((unsigned __int16 **)v5 + 1),
         *((_DWORD *)v5 + 10),
         a2);
LABEL_13:
  TSFree(v5);
  if ( phCryptProvOrNCryptKey && pfCallerFreeProvOrNCryptKey )
    CryptReleaseContext(phCryptProvOrNCryptKey, 0);
  TSFree(v2);
  if ( Destination.Buffer )
    RtlFreeUnicodeString(&Destination);
  return v6;
}

```

## disassembly

```asm
0x1800141bc  mov     [rsp-18h+arg_0], rbx
0x1800141c1  mov     [rsp-18h+arg_8], rsi
0x1800141c6  push    rbp
0x1800141c7  push    rdi
0x1800141c8  push    r14
0x1800141ca  mov     rbp, rsp
0x1800141cd  sub     rsp, 50h
0x1800141d1  xor     esi, esi
0x1800141d3  mov     [rbp+pcbData], 0
0x1800141da  mov     r14, rdx
0x1800141dd  mov     [rbp+phCryptProvOrNCryptKey], 0
0x1800141e5  xorps   xmm0, xmm0
0x1800141e8  mov     [rbp+var_1C], 8
0x1800141ef  lea     r9, [rbp+pcbData]; pcbData
0x1800141f3  mov     [rbp+var_20], 0
0x1800141fa  lea     edx, [rsi+2]; dwPropId
0x1800141fd  mov     [rbp+pdwDataLen], esi
0x180014200  xor     r8d, r8d; pvData
0x180014203  mov     rbx, rcx
0x180014206  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x18001420a  call    cs:__imp_CertGetCertificateContextProperty
0x180014210  test    eax, eax
0x180014212  jnz     short loc_180014220
0x180014214  xor     edi, edi
0x180014216  mov     ebx, 0C0000321h
0x18001421b  jmp     loc_1800142F8
0x180014220  mov     ecx, [rbp+pcbData]; Size
0x180014223  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180014228  mov     rdi, rax
0x18001422b  test    rax, rax
0x18001422e  jnz     short loc_18001423A
0x180014230  mov     ebx, 0C000009Ah
0x180014235  jmp     loc_1800142F8
0x18001423a  lea     r9, [rbp+pcbData]; pcbData
0x18001423e  mov     r8, rdi; pvData
0x180014241  mov     edx, 2; dwPropId
0x180014246  mov     rcx, rbx; pCertContext
0x180014249  call    cs:__imp_CertGetCertificateContextProperty
0x18001424f  test    eax, eax
0x180014251  jz      short loc_180014216
0x180014253  xor     r8d, r8d; pvParameters
0x180014256  lea     rax, [rbp+var_20]
0x18001425a  mov     [rsp+50h+pfCallerFreeProvOrNCryptKey], rax; pfCallerFreeProvOrNCryptKey
0x18001425f  lea     r9, [rbp+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x180014263  lea     rax, [rbp+var_1C]
0x180014267  mov     rcx, rbx; pCert
0x18001426a  mov     [rsp+50h+pdwKeySpec], rax; pdwKeySpec
0x18001426f  lea     edx, [r8+40h]; dwFlags
0x180014273  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x180014279  test    eax, eax
0x18001427b  jz      short loc_180014216
0x18001427d  mov     rcx, [rbp+phCryptProvOrNCryptKey]; hProv
0x180014281  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180014285  xor     r8d, r8d; pbData
0x180014288  mov     dword ptr [rsp+50h+pdwKeySpec], esi; dwFlags
0x18001428c  lea     ebx, [r8+2Bh]
0x180014290  mov     edx, ebx; dwParam
0x180014292  call    cs:__imp_CryptGetProvParam
0x180014298  test    eax, eax
0x18001429a  jz      short loc_1800142D8
0x18001429c  mov     ecx, [rbp+pdwDataLen]; Size
0x18001429f  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x1800142a4  mov     rsi, rax
0x1800142a7  test    rax, rax
0x1800142aa  jz      short loc_1800142D8
0x1800142ac  mov     rcx, [rbp+phCryptProvOrNCryptKey]; hProv
0x1800142b0  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x1800142b4  mov     r8, rax; pbData
0x1800142b7  mov     dword ptr [rsp+50h+pdwKeySpec], 0; dwFlags
0x1800142bf  mov     edx, ebx; dwParam
0x1800142c1  call    cs:__imp_CryptGetProvParam
0x1800142c7  test    eax, eax
0x1800142c9  jz      short loc_1800142D8
0x1800142cb  mov     rdx, rsi; Source
0x1800142ce  lea     rcx, [rbp+Destination]; Destination
0x1800142d2  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x1800142d8  mov     eax, [rdi+28h]
0x1800142db  xor     ecx, ecx; unsigned __int16 *
0x1800142dd  mov     r9, [rdi+8]; unsigned __int16 *
0x1800142e1  mov     r8, [rdi]; unsigned __int16 *
0x1800142e4  mov     rdx, [rbp+Destination.Buffer]; unsigned __int16 *
0x1800142e8  mov     [rsp+50h+pfCallerFreeProvOrNCryptKey], r14; struct _TS_CSPDATA_DETAIL *
0x1800142ed  mov     dword ptr [rsp+50h+pdwKeySpec], eax; unsigned int
0x1800142f1  call    ?TSBuildCspDetail@@YAJPEAG000KPEAU_TS_CSPDATA_DETAIL@@@Z; TSBuildCspDetail(ushort *,ushort *,ushort *,ushort *,ulong,_TS_CSPDATA_DETAIL *)
0x1800142f6  mov     ebx, eax
0x1800142f8  mov     rcx, rdi; void *
0x1800142fb  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x180014300  mov     rcx, [rbp+phCryptProvOrNCryptKey]; hProv
0x180014304  test    rcx, rcx
0x180014307  jz      short loc_180014317
0x180014309  cmp     [rbp+var_20], 0
0x18001430d  jz      short loc_180014317
0x18001430f  xor     edx, edx; dwFlags
0x180014311  call    cs:__imp_CryptReleaseContext
0x180014317  mov     rcx, rsi; void *
0x18001431a  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x18001431f  cmp     [rbp+Destination.Buffer], 0
0x180014324  jz      short loc_180014330
0x180014326  lea     rcx, [rbp+Destination]; UnicodeString
0x18001432a  call    cs:__imp_RtlFreeUnicodeString
0x180014330  mov     rsi, [rsp+50h+arg_8]
0x180014335  mov     eax, ebx
0x180014337  mov     rbx, [rsp+50h+arg_0]
0x18001433c  add     rsp, 50h
0x180014340  pop     r14
0x180014342  pop     rdi
0x180014343  pop     rbp
0x180014344  retn
```
