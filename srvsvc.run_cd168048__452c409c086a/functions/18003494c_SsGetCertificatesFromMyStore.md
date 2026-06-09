# SsGetCertificatesFromMyStore

- ea: `0x18003494c`
- end: `0x180034c08`
- name: `SsGetCertificatesFromMyStore`
- size: `700`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180031c8c`
- `0x180032f00`

## callees

- `0x180020de8`
- `0x180033fc8`
- `0x18003494c`
- `0x180035cf0`
- `0x180035d84`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034be6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034bce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034bce`
- `ntdll!RtlNtStatusToDosError` at `0x180034a05`
- `ntdll!RtlNtStatusToDosError` at `0x180034af0`
- `ntdll!RtlNtStatusToDosError` at `0x180034a05`
- `ntdll!RtlNtStatusToDosError` at `0x180034af0`
- `ntdll!RtlUnicodeToUTF8N` at `0x1800349c2`
- `ntdll!RtlUnicodeToUTF8N` at `0x180034ae2`
- `ntdll!RtlUnicodeToUTF8N` at `0x1800349c2`
- `ntdll!RtlUnicodeToUTF8N` at `0x180034ae2`
- `CRYPT32!CertFreeCertificateContext` at `0x180034b7e`
- `CRYPT32!CertFreeCertificateContext` at `0x180034b7e`
- `CRYPT32!CertCloseStore` at `0x180034bdc`
- `CRYPT32!CertCloseStore` at `0x180034bdc`
- `CRYPT32!CertFindCertificateInStore` at `0x180034aa7`
- `CRYPT32!CertFindCertificateInStore` at `0x180034aa7`
- `CRYPT32!CertOpenStore` at `0x180034a27`
- `CRYPT32!CertOpenStore` at `0x180034a27`

## pseudocode

```c
ULONG __fastcall SsGetCertificatesFromMyStore(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        void *a5,
        __int64 a6)
{
  void *pvPara; // rbx
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r13
  int v12; // eax
  __int64 v13; // r8
  NTSTATUS v14; // esi
  HCERTSTORE v16; // r12
  DWORD LastError; // eax
  ULONG v18; // ebx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  const CERT_CONTEXT *CertificateInStore; // r14
  NTSTATUS v22; // eax
  __int64 v23; // r8
  NTSTATUS v24; // edi
  __int64 v25; // r8
  __int128 pvFindPara; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v27; // [rsp+A0h] [rbp+58h] BYREF
  int v28; // [rsp+A4h] [rbp+5Ch]

  v28 = HIDWORD(a3);
  v27 = 0;
  pvFindPara = 0;
  if ( !a1 )
    return 87;
  if ( !a4 )
    return 87;
  pvPara = a5;
  if ( !a5 )
    return 87;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( *((_WORD *)a5 + v10) );
  v11 = a6;
  v12 = RtlUnicodeToUTF8N(a6 + 8, 128, &v27, a5, 2 * (int)v10);
  v14 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v13, v27, v12);
    }
    return RtlNtStatusToDosError(v14);
  }
  v16 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x20000u, pvPara);
  if ( !v16 )
    return GetLastError();
  LastError = SsConvertCryptStringToBinary(a4, (DWORD *)&pvFindPara);
  v18 = LastError;
  if ( LastError )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_37;
    }
    v20 = 20;
    goto LABEL_36;
  }
  CertificateInStore = CertFindCertificateInStore(v16, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
  if ( CertificateInStore )
  {
    do
      ++v9;
    while ( *(_WORD *)(a1 + 2 * v9) );
    v22 = RtlUnicodeToUTF8N(v11 + 140, 256, &v27, a1, 2 * (int)v9);
    v24 = v22;
    if ( v22 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, v23, v11 + 140);
      }
      memcpy_0((void *)(v11 + 140 + v27 + 1LL), *((const void **)&pvFindPara + 1), (unsigned int)pvFindPara);
      *(_DWORD *)(v11 + 136) += 276;
    }
    else
    {
      v18 = RtlNtStatusToDosError(v22);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v25, v27, v24);
      }
    }
    CertFreeCertificateContext(CertificateInStore);
    goto LABEL_37;
  }
  LastError = GetLastError();
  v18 = LastError;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v20 = 23;
LABEL_36:
    WPP_SF_d(v19[2], v20, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, LastError);
  }
LABEL_37:
  if ( *((_QWORD *)&pvFindPara + 1) )
    LocalFree(*((HLOCAL *)&pvFindPara + 1));
  if ( !CertCloseStore(v16, 2u) )
    return GetLastError();
  return v18;
}

```

## disassembly

```asm
0x18003494c  mov     [rsp-40h+arg_10], r8
0x180034951  push    rbp
0x180034952  push    rbx
0x180034953  push    rsi
0x180034954  push    rdi
0x180034955  push    r12
0x180034957  push    r13
0x180034959  push    r14
0x18003495b  push    r15
0x18003495d  mov     rbp, rsp
0x180034960  sub     rsp, 48h
0x180034964  xor     r12d, r12d
0x180034967  xorps   xmm0, xmm0
0x18003496a  mov     dword ptr [rbp+arg_10], r12d
0x18003496e  mov     r14, r9
0x180034971  mov     r15, rcx
0x180034974  movups  [rbp+pvFindPara], xmm0
0x180034978  test    rcx, rcx
0x18003497b  jz      loc_180034BF2
0x180034981  test    r9, r9
0x180034984  jz      loc_180034BF2
0x18003498a  mov     rbx, [rbp+arg_20]
0x18003498e  test    rbx, rbx
0x180034991  jz      loc_180034BF2
0x180034997  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003499b  mov     rax, rdi
0x18003499e  inc     rax
0x1800349a1  cmp     [rbx+rax*2], r12w
0x1800349a6  jnz     short loc_18003499E
0x1800349a8  mov     r13, [rbp+arg_28]
0x1800349ac  lea     r8, [rbp+arg_10]
0x1800349b0  add     eax, eax
0x1800349b2  mov     r9, rbx
0x1800349b5  mov     edx, 80h
0x1800349ba  mov     dword ptr [rsp+48h+pvPara], eax
0x1800349be  lea     rcx, [r13+8]
0x1800349c2  call    cs:__imp_RtlUnicodeToUTF8N
0x1800349c8  mov     esi, eax
0x1800349ca  test    eax, eax
0x1800349cc  jns     short loc_180034A10
0x1800349ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800349d5  lea     rdx, WPP_GLOBAL_Control
0x1800349dc  cmp     rcx, rdx
0x1800349df  jz      short loc_180034A03
0x1800349e1  test    byte ptr [rcx+1Ch], 1
0x1800349e5  jz      short loc_180034A03
0x1800349e7  cmp     byte ptr [rcx+19h], 1
0x1800349eb  jb      short loc_180034A03
0x1800349ed  mov     r9d, dword ptr [rbp+arg_10]
0x1800349f1  mov     edx, 13h
0x1800349f6  mov     rcx, [rcx+10h]
0x1800349fa  mov     dword ptr [rsp+48h+pvPara], eax
0x1800349fe  call    WPP_SF_dd
0x180034a03  mov     ecx, esi; Status
0x180034a05  call    cs:__imp_RtlNtStatusToDosError
0x180034a0b  jmp     loc_180034BF7
0x180034a10  xor     r8d, r8d; hCryptProv
0x180034a13  mov     [rsp+48h+pvPara], rbx; pvPara
0x180034a18  mov     r9d, 20000h; dwFlags
0x180034a1e  mov     edx, 10001h; dwEncodingType
0x180034a23  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180034a27  call    cs:__imp_CertOpenStore
0x180034a2d  xor     esi, esi
0x180034a2f  mov     r12, rax
0x180034a32  test    rax, rax
0x180034a35  jnz     short loc_180034A42
0x180034a37  call    cs:__imp_GetLastError
0x180034a3d  jmp     loc_180034BF7
0x180034a42  lea     rdx, [rbp+pvFindPara]; pcbBinary
0x180034a46  mov     rcx, r14; pszString
0x180034a49  call    SsConvertCryptStringToBinary
0x180034a4e  mov     ebx, eax
0x180034a50  test    eax, eax
0x180034a52  jz      short loc_180034A89
0x180034a54  mov     rcx, cs:WPP_GLOBAL_Control
0x180034a5b  lea     rdx, WPP_GLOBAL_Control
0x180034a62  cmp     rcx, rdx
0x180034a65  jz      loc_180034BC5
0x180034a6b  test    byte ptr [rcx+1Ch], 1
0x180034a6f  jz      loc_180034BC5
0x180034a75  cmp     byte ptr [rcx+19h], 1
0x180034a79  jb      loc_180034BC5
0x180034a7f  mov     edx, 14h
0x180034a84  jmp     loc_180034BB2
0x180034a89  mov     r9d, 10000h; dwFindType
0x180034a8f  mov     [rsp+48h+pPrevCertContext], rsi; pPrevCertContext
0x180034a94  lea     rax, [rbp+pvFindPara]
0x180034a98  xor     r8d, r8d; dwFindFlags
0x180034a9b  mov     rcx, r12; hCertStore
0x180034a9e  mov     [rsp+48h+pvPara], rax; pvFindPara
0x180034aa3  lea     edx, [r9+1]; dwCertEncodingType
0x180034aa7  call    cs:__imp_CertFindCertificateInStore
0x180034aad  mov     r14, rax
0x180034ab0  test    rax, rax
0x180034ab3  jz      loc_180034B86
0x180034ab9  lea     rsi, [r13+8Ch]
0x180034ac0  xor     eax, eax
0x180034ac2  inc     rdi
0x180034ac5  cmp     [r15+rdi*2], ax
0x180034aca  jnz     short loc_180034AC2
0x180034acc  lea     eax, [rdi+rdi]
0x180034acf  mov     r9, r15
0x180034ad2  lea     r8, [rbp+arg_10]
0x180034ad6  mov     dword ptr [rsp+48h+pvPara], eax
0x180034ada  mov     edx, 100h
0x180034adf  mov     rcx, rsi
0x180034ae2  call    cs:__imp_RtlUnicodeToUTF8N
0x180034ae8  mov     edi, eax
0x180034aea  test    eax, eax
0x180034aec  jns     short loc_180034B2F
0x180034aee  mov     ecx, eax; Status
0x180034af0  call    cs:__imp_RtlNtStatusToDosError
0x180034af6  mov     ebx, eax
0x180034af8  mov     rcx, cs:WPP_GLOBAL_Control
0x180034aff  lea     rdx, WPP_GLOBAL_Control
0x180034b06  cmp     rcx, rdx
0x180034b09  jz      short loc_180034B7B
0x180034b0b  test    byte ptr [rcx+1Ch], 1
0x180034b0f  jz      short loc_180034B7B
0x180034b11  cmp     byte ptr [rcx+19h], 1
0x180034b15  jb      short loc_180034B7B
0x180034b17  mov     r9d, dword ptr [rbp+arg_10]
0x180034b1b  mov     edx, 15h
0x180034b20  mov     rcx, [rcx+10h]
0x180034b24  mov     dword ptr [rsp+48h+pvPara], edi
0x180034b28  call    WPP_SF_dd
0x180034b2d  jmp     short loc_180034B7B
0x180034b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034b36  lea     rdx, WPP_GLOBAL_Control
0x180034b3d  cmp     rcx, rdx
0x180034b40  jz      short loc_180034B5A
0x180034b42  test    byte ptr [rcx+1Ch], 1
0x180034b46  jz      short loc_180034B5A
0x180034b48  cmp     byte ptr [rcx+19h], 2
0x180034b4c  jb      short loc_180034B5A
0x180034b4e  mov     rcx, [rcx+10h]
0x180034b52  mov     r9, rsi
0x180034b55  call    WPP_SF_s
0x180034b5a  mov     ecx, dword ptr [rbp+arg_10]
0x180034b5d  mov     r8d, dword ptr [rbp+pvFindPara]; Size
0x180034b61  inc     rcx
0x180034b64  mov     rdx, qword ptr [rbp+pvFindPara+8]; Src
0x180034b68  add     rcx, rsi; void *
0x180034b6b  call    memcpy_0
0x180034b70  add     dword ptr [r13+88h], 114h
0x180034b7b  mov     rcx, r14; pCertContext
0x180034b7e  call    cs:__imp_CertFreeCertificateContext
0x180034b84  jmp     short loc_180034BC5
0x180034b86  call    cs:__imp_GetLastError
0x180034b8c  mov     ebx, eax
0x180034b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180034b95  lea     rdx, WPP_GLOBAL_Control
0x180034b9c  cmp     rcx, rdx
0x180034b9f  jz      short loc_180034BC5
0x180034ba1  test    byte ptr [rcx+1Ch], 1
0x180034ba5  jz      short loc_180034BC5
0x180034ba7  cmp     byte ptr [rcx+19h], 1
0x180034bab  jb      short loc_180034BC5
0x180034bad  mov     edx, 17h
0x180034bb2  mov     rcx, [rcx+10h]
0x180034bb6  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x180034bbd  mov     r9d, eax
0x180034bc0  call    WPP_SF_d
0x180034bc5  mov     rcx, qword ptr [rbp+pvFindPara+8]; hMem
0x180034bc9  test    rcx, rcx
0x180034bcc  jz      short loc_180034BD4
0x180034bce  call    cs:__imp_LocalFree
0x180034bd4  mov     edx, 2; dwFlags
0x180034bd9  mov     rcx, r12; hCertStore
0x180034bdc  call    cs:__imp_CertCloseStore
0x180034be2  test    eax, eax
0x180034be4  jnz     short loc_180034BEE
0x180034be6  call    cs:__imp_GetLastError
0x180034bec  mov     ebx, eax
0x180034bee  mov     eax, ebx
0x180034bf0  jmp     short loc_180034BF7
0x180034bf2  mov     eax, 57h ; 'W'
0x180034bf7  add     rsp, 48h
0x180034bfb  pop     r15
0x180034bfd  pop     r14
0x180034bff  pop     r13
0x180034c01  pop     r12
0x180034c03  pop     rdi
0x180034c04  pop     rsi
0x180034c05  pop     rbx
0x180034c06  pop     rbp
0x180034c07  retn
```
