# CSslCredential::DeleteCredential(void)

- ea: `0x180041458`
- end: `0x1800415a6`
- name: `?DeleteCredential@CSslCredential@@AEAAXXZ`
- size: `334`
- prototype: `void __fastcall(CSslCredential *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180041428`

## callees

- `0x180014240`
- `0x180041458`
- `0x1800415ac`
- `0x180053ff8`
- `0x180078d00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800414f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800414f6`
- `ntdll!RtlDeleteResource` at `0x180041590`
- `ntdll!RtlDeleteResource` at `0x180041590`
- `ncrypt!NCryptFreeObject` at `0x180041536`
- `ncrypt!NCryptFreeObject` at `0x180041536`
- `CRYPT32!CertFreeCertificateContext` at `0x1800414a7`
- `CRYPT32!CertFreeCertificateContext` at `0x1800414a7`
- `CRYPT32!CertCloseServerOcspResponse` at `0x180041489`
- `CRYPT32!CertCloseServerOcspResponse` at `0x180041489`
- `CRYPT32!CertFreeCertificateChain` at `0x180041498`
- `CRYPT32!CertFreeCertificateChain` at `0x180041498`

## pseudocode

```c
void __fastcall CSslCredential::DeleteCredential(CSslCredential *this)
{
  void *v2; // rcx
  void *v3; // rcx
  const CERT_CHAIN_CONTEXT *v4; // rcx
  const CERT_CONTEXT *v5; // rcx
  void **v6; // rsi
  void *v7; // rdi
  void **v8; // rax
  NCRYPT_HANDLE v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx

  v2 = (void *)*((_QWORD *)this + 54);
  if ( v2 )
    SPExternalFree(v2);
  v3 = (void *)*((_QWORD *)this + 57);
  if ( v3 )
    CertCloseServerOcspResponse(v3, 0);
  v4 = (const CERT_CHAIN_CONTEXT *)*((_QWORD *)this + 8);
  if ( v4 )
    CertFreeCertificateChain(v4);
  v5 = (const CERT_CONTEXT *)*((_QWORD *)this + 4);
  if ( v5 )
    CertFreeCertificateContext(v5);
  CSslCredential::ReleaseEphemeralKeyData(*((struct EphemeralKey **)this + 62));
  CSslCredential::ReleaseEphemeralKeyData(*((struct EphemeralKey **)this + 63));
  v6 = (void **)((char *)this + 480);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == v6 )
      break;
    if ( *((void ***)v7 + 1) != v6 || (v8 = *(void ***)v7, *(void **)(*(_QWORD *)v7 + 8LL) != v7) )
      __fastfail(3u);
    *v6 = v8;
    v8[1] = v6;
    CSslCredential::ReleaseEphemeralKeyData(*((struct EphemeralKey **)v7 + 3));
    LocalFree(v7);
  }
  CSslCredential::DeleteLocalServerKeys(this);
  if ( *((_BYTE *)this + 79) )
  {
LABEL_19:
    if ( *((_BYTE *)this + 78) )
      goto LABEL_22;
    goto LABEL_20;
  }
  if ( *((_BYTE *)this + 78) )
  {
    if ( !*((_BYTE *)this + 120) )
      CSslCredential::RemoteCloseKeyHandle(this);
    goto LABEL_19;
  }
LABEL_20:
  v9 = *((_QWORD *)this + 13);
  if ( v9 )
    NCryptFreeObject(v9);
LABEL_22:
  v10 = (void *)*((_QWORD *)this + 55);
  if ( v10 )
    SPExternalFree(v10);
  v11 = (void *)*((_QWORD *)this + 52);
  if ( v11 )
    SPExternalFree(v11);
  v12 = (void *)*((_QWORD *)this + 50);
  if ( v12 )
    SPExternalFree(v12);
  v13 = (void *)*((_QWORD *)this + 58);
  if ( v13 )
    SPExternalFree(v13);
  if ( *((_BYTE *)this + 648) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 552));
}

```

## disassembly

```asm
0x180041458  mov     [rsp+arg_0], rbx
0x18004145d  mov     [rsp+arg_8], rsi
0x180041462  push    rdi
0x180041463  sub     rsp, 20h
0x180041467  mov     rbx, rcx
0x18004146a  mov     rcx, [rcx+1B0h]; void *
0x180041471  test    rcx, rcx
0x180041474  jz      short loc_18004147B
0x180041476  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18004147b  mov     rcx, [rbx+1C8h]; hServerOcspResponse
0x180041482  test    rcx, rcx
0x180041485  jz      short loc_18004148F
0x180041487  xor     edx, edx; dwFlags
0x180041489  call    cs:__imp_CertCloseServerOcspResponse
0x18004148f  mov     rcx, [rbx+40h]; pChainContext
0x180041493  test    rcx, rcx
0x180041496  jz      short loc_18004149E
0x180041498  call    cs:__imp_CertFreeCertificateChain
0x18004149e  mov     rcx, [rbx+20h]; pCertContext
0x1800414a2  test    rcx, rcx
0x1800414a5  jz      short loc_1800414AD
0x1800414a7  call    cs:__imp_CertFreeCertificateContext
0x1800414ad  mov     rcx, [rbx+1F0h]; struct EphemeralKey *
0x1800414b4  call    ?ReleaseEphemeralKeyData@CSslCredential@@SAXPEAVEphemeralKey@@@Z; CSslCredential::ReleaseEphemeralKeyData(EphemeralKey *)
0x1800414b9  mov     rcx, [rbx+1F8h]; struct EphemeralKey *
0x1800414c0  call    ?ReleaseEphemeralKeyData@CSslCredential@@SAXPEAVEphemeralKey@@@Z; CSslCredential::ReleaseEphemeralKeyData(EphemeralKey *)
0x1800414c5  lea     rsi, [rbx+1E0h]
0x1800414cc  mov     rdi, [rsi]
0x1800414cf  cmp     rdi, rsi
0x1800414d2  jz      short loc_180041505
0x1800414d4  cmp     [rdi+8], rsi
0x1800414d8  jnz     short loc_1800414FE
0x1800414da  mov     rax, [rdi]
0x1800414dd  cmp     [rax+8], rdi
0x1800414e1  jnz     short loc_1800414FE
0x1800414e3  mov     [rsi], rax
0x1800414e6  mov     [rax+8], rsi
0x1800414ea  mov     rcx, [rdi+18h]; struct EphemeralKey *
0x1800414ee  call    ?ReleaseEphemeralKeyData@CSslCredential@@SAXPEAVEphemeralKey@@@Z; CSslCredential::ReleaseEphemeralKeyData(EphemeralKey *)
0x1800414f3  mov     rcx, rdi; hMem
0x1800414f6  call    cs:__imp_LocalFree
0x1800414fc  jmp     short loc_1800414CC
0x1800414fe  mov     ecx, 3
0x180041503  int     29h; Win8: RtlFailFast(ecx)
0x180041505  mov     rcx, rbx; this
0x180041508  call    ?DeleteLocalServerKeys@CSslCredential@@AEAAXXZ; CSslCredential::DeleteLocalServerKeys(void)
0x18004150d  cmp     byte ptr [rbx+4Fh], 0
0x180041511  jnz     short loc_180041527
0x180041513  cmp     byte ptr [rbx+4Eh], 0
0x180041517  jz      short loc_18004152D
0x180041519  cmp     byte ptr [rbx+78h], 0
0x18004151d  jnz     short loc_180041527
0x18004151f  mov     rcx, rbx; this
0x180041522  call    ?RemoteCloseKeyHandle@CSslCredential@@QEAAXXZ; CSslCredential::RemoteCloseKeyHandle(void)
0x180041527  cmp     byte ptr [rbx+4Eh], 0
0x18004152b  jnz     short loc_18004153C
0x18004152d  mov     rcx, [rbx+68h]; hObject
0x180041531  test    rcx, rcx
0x180041534  jz      short loc_18004153C
0x180041536  call    cs:__imp_NCryptFreeObject
0x18004153c  mov     rcx, [rbx+1B8h]; void *
0x180041543  test    rcx, rcx
0x180041546  jz      short loc_18004154D
0x180041548  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18004154d  mov     rcx, [rbx+1A0h]; void *
0x180041554  test    rcx, rcx
0x180041557  jz      short loc_18004155E
0x180041559  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18004155e  mov     rcx, [rbx+190h]; void *
0x180041565  test    rcx, rcx
0x180041568  jz      short loc_18004156F
0x18004156a  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18004156f  mov     rcx, [rbx+1D0h]; void *
0x180041576  test    rcx, rcx
0x180041579  jz      short loc_180041580
0x18004157b  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x180041580  cmp     byte ptr [rbx+288h], 0
0x180041587  jz      short loc_180041596
0x180041589  lea     rcx, [rbx+228h]; Resource
0x180041590  call    cs:__imp_RtlDeleteResource
0x180041596  mov     rbx, [rsp+28h+arg_0]
0x18004159b  mov     rsi, [rsp+28h+arg_8]
0x1800415a0  add     rsp, 20h
0x1800415a4  pop     rdi
0x1800415a5  retn
```
