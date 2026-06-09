# TSGetPublicKeyFromCertFormat(ulong,_SecBuffer *,uchar * *,ulong *)

- ea: `0x180005520`
- end: `0x1800057bd`
- name: `?TSGetPublicKeyFromCertFormat@@YAJKPEAU_SecBuffer@@PEAPEAEPEAK@Z`
- size: `669`
- prototype: `__int64 __fastcall(unsigned int, struct _SecBuffer *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001160`

## callees

- `0x180005520`
- `0x18000c1a4`
- `0x180018fb0`
- `0x180019e1c`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x1800057b2`
- `CRYPT32!CertFreeCertificateContext` at `0x1800057b2`
- `CRYPT32!CertCreateCertificateContext` at `0x1800055af`
- `CRYPT32!CertCreateCertificateContext` at `0x1800055af`

## pseudocode

```c
__int64 __fastcall TSGetPublicKeyFromCertFormat(
        unsigned int a1,
        struct _SecBuffer *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  unsigned __int8 *v4; // rbx
  struct _CERT_CONTEXT *v5; // rsi
  unsigned int cbBuffer; // r9d
  char *pvBuffer; // rcx
  DWORD v11; // r8d
  PCCERT_CONTEXT CertificateContext; // rax
  int v13; // edi
  size_t cbData; // rbp
  unsigned __int8 *v16; // r12
  unsigned __int8 *v17; // rax
  unsigned int v18; // edx
  unsigned __int16 *v19; // r8
  int v20; // eax
  int v21; // eax
  struct _CERT_CONTEXT *v22; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 *v23; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v24; // [rsp+78h] [rbp+10h] BYREF

  v4 = 0;
  v5 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  if ( !a2 )
    return 3221225485LL;
  if ( !a3 )
    return 3221225485LL;
  if ( !a4 )
    return 3221225485LL;
  cbBuffer = a2->cbBuffer;
  if ( a2->cbBuffer <= 0xC )
    return 3221225485LL;
  pvBuffer = (char *)a2->pvBuffer;
  if ( *(_DWORD *)pvBuffer != 3 )
  {
    v18 = *(_DWORD *)pvBuffer - 1;
    if ( *(_DWORD *)pvBuffer == 1 )
    {
      if ( cbBuffer < 0x34 )
      {
        v13 = -1073741811;
        goto LABEL_15;
      }
      if ( *((_DWORD *)pvBuffer + 1) != 40 )
      {
        v13 = -1073741811;
        goto LABEL_15;
      }
      v19 = L"MY";
    }
    else
    {
      if ( *(_DWORD *)pvBuffer != 2 )
      {
        v13 = -1073741811;
        goto LABEL_15;
      }
      if ( cbBuffer < 0x134 )
      {
        v13 = -1073741811;
        goto LABEL_15;
      }
      if ( *((_DWORD *)pvBuffer + 1) != 296 )
      {
        v13 = -1073741811;
        goto LABEL_15;
      }
      v19 = (unsigned __int16 *)(pvBuffer + 44);
      *((_WORD *)pvBuffer + 149) = 0;
    }
    v20 = TSGetCertificateByHash(
            (unsigned __int8 *)pvBuffer + 24,
            v18,
            v19,
            *((_DWORD *)pvBuffer + 3) & 1,
            (const struct _CERT_CONTEXT **)&v22);
    v5 = v22;
    v13 = v20;
    if ( v20 < 0 )
      goto LABEL_13;
    goto LABEL_21;
  }
  v11 = *((_DWORD *)pvBuffer + 1);
  if ( v11 >= 0xFFFFFFF4 )
  {
    v13 = -1073741675;
  }
  else
  {
    if ( cbBuffer >= v11 + 12 )
    {
      if ( pvBuffer == (char *)-8LL || !v11 )
      {
        v13 = -1073741811;
        goto LABEL_13;
      }
      CertificateContext = CertCreateCertificateContext(1u, (const BYTE *)pvBuffer + 8, v11);
      if ( CertificateContext )
      {
        v13 = 0;
        v5 = (struct _CERT_CONTEXT *)CertificateContext;
      }
      else
      {
        v13 = -1073741811;
      }
      if ( v13 < 0 )
      {
LABEL_13:
        if ( v5 )
          CertFreeCertificateContext(v5);
        goto LABEL_15;
      }
LABEL_21:
      if ( a1 <= 1 )
      {
        v21 = TSPublicKeyFromCert(v5, &v23, &v24);
        v4 = v23;
        v13 = v21;
        if ( v21 < 0 )
          goto LABEL_13;
        LODWORD(cbData) = v24;
LABEL_26:
        *a3 = v4;
        v4 = 0;
        *a4 = cbData;
        goto LABEL_13;
      }
      cbData = v5->pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData;
      if ( TSGlobalState == 1 )
      {
        v16 = (unsigned __int8 *)((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocatePrivateHeap)((unsigned int)cbData);
      }
      else
      {
        v17 = (unsigned __int8 *)((__int64 (__fastcall *)(_QWORD))TSGlobalDllFunctions->AllocateHeap)((unsigned int)cbData);
        v16 = v17;
        if ( v17 )
        {
          memset_0(v17, 0, cbData);
          v4 = v16;
LABEL_25:
          memcpy_0(v16, v5->pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData, cbData);
          goto LABEL_26;
        }
      }
      v4 = v16;
      if ( !v16 )
      {
        v13 = -1073741670;
        goto LABEL_13;
      }
      goto LABEL_25;
    }
    v13 = -1073741811;
  }
LABEL_15:
  if ( v4 )
  {
    if ( TSGlobalState == 1 )
      ((void (__fastcall *)(unsigned __int8 *))TSGlobalLsaFunctions->FreePrivateHeap)(v4);
    else
      ((void (__fastcall *)(unsigned __int8 *))TSGlobalDllFunctions->FreeHeap)(v4);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180005520  mov     [rsp+arg_10], rbx
0x180005525  push    rbp
0x180005526  push    rsi
0x180005527  push    rdi
0x180005528  push    r14
0x18000552a  push    r15
0x18000552c  sub     rsp, 40h
0x180005530  xor     ebx, ebx
0x180005532  xor     esi, esi
0x180005534  mov     [rsp+68h+var_38], rsi
0x180005539  mov     r14, r9
0x18000553c  mov     [rsp+68h+var_30], rbx
0x180005541  mov     r15, r8
0x180005544  mov     [rsp+68h+arg_8], ebx
0x180005548  mov     ebp, ecx
0x18000554a  test    rdx, rdx
0x18000554d  jz      loc_180005683
0x180005553  test    r8, r8
0x180005556  jz      loc_180005683
0x18000555c  test    r9, r9
0x18000555f  jz      loc_180005683
0x180005565  mov     r9d, [rdx]
0x180005568  cmp     r9d, 0Ch
0x18000556c  jbe     loc_180005683
0x180005572  mov     rcx, [rdx+8]
0x180005576  mov     [rsp+68h+arg_0], r12
0x18000557b  mov     edx, [rcx]
0x18000557d  cmp     edx, 3
0x180005580  jnz     loc_1800056C8
0x180005586  mov     r8d, [rcx+4]; cbCertEncoded
0x18000558a  lea     eax, [r8+0Ch]
0x18000558e  cmp     eax, 0Ch
0x180005591  jb      short loc_1800055F0
0x180005593  cmp     r9d, eax
0x180005596  jb      loc_180005767
0x18000559c  lea     rdx, [rcx+8]; pbCertEncoded
0x1800055a0  test    rdx, rdx
0x1800055a3  jz      short loc_18000561C
0x1800055a5  test    r8d, r8d
0x1800055a8  jz      short loc_18000561C
0x1800055aa  mov     ecx, 1; dwCertEncodingType
0x1800055af  call    cs:__imp_CertCreateCertificateContext
0x1800055b5  test    rax, rax
0x1800055b8  jz      loc_180005771
0x1800055be  xor     edi, edi
0x1800055c0  mov     rsi, rax
0x1800055c3  test    edi, edi
0x1800055c5  jns     short loc_180005623
0x1800055c7  test    rsi, rsi
0x1800055ca  jnz     loc_1800057AF
0x1800055d0  mov     r12, [rsp+68h+arg_0]
0x1800055d5  test    rbx, rbx
0x1800055d8  jnz     short loc_1800055F7
0x1800055da  mov     eax, edi
0x1800055dc  mov     rbx, [rsp+68h+arg_10]
0x1800055e4  add     rsp, 40h
0x1800055e8  pop     r15
0x1800055ea  pop     r14
0x1800055ec  pop     rdi
0x1800055ed  pop     rsi
0x1800055ee  pop     rbp
0x1800055ef  retn
0x1800055f0  mov     edi, 0C0000095h
0x1800055f5  jmp     short loc_1800055D0
0x1800055f7  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800055fe  mov     rcx, rbx
0x180005601  jnz     loc_18000568D
0x180005607  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18000560e  mov     rax, [rax+188h]
0x180005615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000561a  jmp     short loc_1800055DA
0x18000561c  mov     edi, 0C000000Dh
0x180005621  jmp     short loc_1800055C7
0x180005623  cmp     ebp, 1
0x180005626  jbe     loc_180005785
0x18000562c  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180005633  mov     rax, [rsi+18h]
0x180005637  mov     ebp, [rax+78h]
0x18000563a  jnz     short loc_18000569D
0x18000563c  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180005643  mov     ecx, ebp
0x180005645  mov     rax, [rax+180h]
0x18000564c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005651  mov     r12, rax
0x180005654  mov     rbx, r12
0x180005657  test    r12, r12
0x18000565a  jz      loc_18000577B
0x180005660  mov     rdx, [rsi+18h]
0x180005664  mov     r8, rbp; Size
0x180005667  mov     rcx, r12; void *
0x18000566a  mov     rdx, [rdx+80h]; Src
0x180005671  call    memcpy_0
0x180005676  mov     [r15], rbx
0x180005679  xor     ebx, ebx
0x18000567b  mov     [r14], ebp
0x18000567e  jmp     loc_1800055C7
0x180005683  mov     eax, 0C000000Dh
0x180005688  jmp     loc_1800055DC
0x18000568d  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180005694  mov     rax, [rax+8]
0x180005698  jmp     loc_180005615
0x18000569d  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x1800056a4  mov     ecx, ebp
0x1800056a6  mov     rax, [rax]
0x1800056a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ae  mov     r12, rax
0x1800056b1  test    rax, rax
0x1800056b4  jz      short loc_180005654
0x1800056b6  mov     r8, rbp; Size
0x1800056b9  xor     edx, edx; Val
0x1800056bb  mov     rcx, rax; void *
0x1800056be  call    memset_0
0x1800056c3  mov     rbx, r12
0x1800056c6  jmp     short loc_180005660
0x1800056c8  sub     edx, 1; unsigned int
0x1800056cb  jz      short loc_180005711
0x1800056cd  cmp     edx, 1
0x1800056d0  jz      short loc_1800056DC
0x1800056d2  mov     edi, 0C000000Dh
0x1800056d7  jmp     loc_1800055D0
0x1800056dc  cmp     r9d, 134h
0x1800056e3  jnb     short loc_1800056EF
0x1800056e5  mov     edi, 0C000000Dh
0x1800056ea  jmp     loc_1800055D0
0x1800056ef  cmp     dword ptr [rcx+4], 128h
0x1800056f6  jz      short loc_180005702
0x1800056f8  mov     edi, 0C000000Dh
0x1800056fd  jmp     loc_1800055D0
0x180005702  xor     eax, eax
0x180005704  lea     r8, [rcx+2Ch]
0x180005708  mov     [rcx+12Ah], ax
0x18000570f  jmp     short loc_180005738
0x180005711  cmp     r9d, 34h ; '4'
0x180005715  jnb     short loc_180005721
0x180005717  mov     edi, 0C000000Dh
0x18000571c  jmp     loc_1800055D0
0x180005721  cmp     dword ptr [rcx+4], 28h ; '('
0x180005725  jz      short loc_180005731
0x180005727  mov     edi, 0C000000Dh
0x18000572c  jmp     loc_1800055D0
0x180005731  lea     r8, aMy; "MY"
0x180005738  mov     r9d, [rcx+0Ch]
0x18000573c  lea     rax, [rsp+68h+var_38]
0x180005741  and     r9d, 1; int
0x180005745  mov     [rsp+68h+var_48], rax; struct _CERT_CONTEXT **
0x18000574a  add     rcx, 18h; unsigned __int8 *
0x18000574e  call    ?TSGetCertificateByHash@@YAJPEAEKPEAGHPEAPEBU_CERT_CONTEXT@@@Z; TSGetCertificateByHash(uchar *,ulong,ushort *,int,_CERT_CONTEXT const * *)
0x180005753  mov     rsi, [rsp+68h+var_38]
0x180005758  mov     edi, eax
0x18000575a  test    eax, eax
0x18000575c  jns     loc_180005623
0x180005762  jmp     loc_1800055C7
0x180005767  mov     edi, 0C000000Dh
0x18000576c  jmp     loc_1800055D0
0x180005771  mov     edi, 0C000000Dh
0x180005776  jmp     loc_1800055C3
0x18000577b  mov     edi, 0C000009Ah
0x180005780  jmp     loc_1800055C7
0x180005785  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x18000578a  mov     rcx, rsi; struct _CERT_CONTEXT *
0x18000578d  lea     rdx, [rsp+68h+var_30]; unsigned __int8 **
0x180005792  call    ?TSPublicKeyFromCert@@YAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z; TSPublicKeyFromCert(_CERT_CONTEXT const *,uchar * *,ulong *)
0x180005797  mov     rbx, [rsp+68h+var_30]
0x18000579c  mov     edi, eax
0x18000579e  test    eax, eax
0x1800057a0  js      loc_1800055C7
0x1800057a6  mov     ebp, [rsp+68h+arg_8]
0x1800057aa  jmp     loc_180005676
0x1800057af  mov     rcx, rsi; pCertContext
0x1800057b2  call    cs:__imp_CertFreeCertificateContext
0x1800057b8  jmp     loc_1800055D0
```
