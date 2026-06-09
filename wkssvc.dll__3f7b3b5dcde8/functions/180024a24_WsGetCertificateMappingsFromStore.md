# WsGetCertificateMappingsFromStore

- ea: `0x180024a24`
- end: `0x180024ce2`
- name: `WsGetCertificateMappingsFromStore`
- size: `702`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180020d14`
- `0x180021ff0`

## callees

- `0x1800211fc`
- `0x180022b7c`
- `0x180023640`
- `0x1800236d4`
- `0x180024a24`
- `0x180033159`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180024add`
- `ntdll!RtlNtStatusToDosError` at `0x180024bda`
- `ntdll!RtlNtStatusToDosError` at `0x180024add`
- `ntdll!RtlNtStatusToDosError` at `0x180024bda`
- `ntdll!RtlUnicodeToUTF8N` at `0x180024a9a`
- `ntdll!RtlUnicodeToUTF8N` at `0x180024bcc`
- `ntdll!RtlUnicodeToUTF8N` at `0x180024a9a`
- `ntdll!RtlUnicodeToUTF8N` at `0x180024bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024cc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024caf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024caf`
- `CRYPT32!CertOpenStore` at `0x180024b01`
- `CRYPT32!CertOpenStore` at `0x180024b01`
- `CRYPT32!CertFindCertificateInStore` at `0x180024b91`
- `CRYPT32!CertFindCertificateInStore` at `0x180024b91`
- `CRYPT32!CertCloseStore` at `0x180024cbd`
- `CRYPT32!CertCloseStore` at `0x180024cbd`
- `CRYPT32!CertFreeCertificateContext` at `0x180024c68`
- `CRYPT32!CertFreeCertificateContext` at `0x180024c68`

## pseudocode

```c
__int64 __fastcall WsGetCertificateMappingsFromStore(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        void *a5,
        __int64 a6)
{
  HCERTSTORE v8; // r13
  void *v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // r15
  NTSTATUS v13; // esi
  __int64 v14; // r8
  ULONG LastError; // eax
  ULONG v16; // ebx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  const CERT_CONTEXT *CertificateInStore; // r14
  NTSTATUS v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  NTSTATUS v23; // edi
  __int64 v24; // r8
  int pvPara; // [rsp+20h] [rbp-28h]
  __int128 pvFindPara; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v28; // [rsp+A0h] [rbp+58h] BYREF
  int v29; // [rsp+A4h] [rbp+5Ch]

  v29 = HIDWORD(a3);
  v28 = 0;
  v8 = 0;
  pvFindPara = 0;
  if ( a1 && a4 && (v9 = a5) != 0 )
  {
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)a5 + v11) );
    v12 = a6;
    v13 = RtlUnicodeToUTF8N(a6 + 8, 128, &v28);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, v14, v28, v13);
      }
      LastError = RtlNtStatusToDosError(v13);
      goto LABEL_12;
    }
    v8 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x28000u, v9);
    if ( !v8 )
    {
      LastError = GetLastError();
LABEL_12:
      v16 = LastError;
      goto LABEL_39;
    }
    v16 = LmConvertCryptStringToBinary(a4, (DWORD *)&pvFindPara);
    if ( v16 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v18 = 50;
LABEL_20:
        WPP_SF_d(v17[2], v18, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, v16);
      }
    }
    else
    {
      CertificateInStore = CertFindCertificateInStore(v8, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
      if ( CertificateInStore )
      {
        do
          ++v10;
        while ( *(_WORD *)(a1 + 2 * v10) );
        pvPara = 2 * v10;
        v20 = RtlUnicodeToUTF8N(v12 + 140, 256, &v28);
        v23 = v20;
        if ( v20 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, v12 + 140, pvPara);
          }
          memcpy_0((void *)(v12 + 140 + v28 + 1LL), *((const void **)&pvFindPara + 1), (unsigned int)pvFindPara);
          *(_DWORD *)(v12 + 136) += 276;
        }
        else
        {
          v16 = RtlNtStatusToDosError(v20);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, v24, v28, v23);
          }
        }
        CertFreeCertificateContext(CertificateInStore);
      }
      else
      {
        v16 = GetLastError();
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v18 = 53;
          goto LABEL_20;
        }
      }
    }
  }
  else
  {
    v16 = 87;
  }
LABEL_39:
  if ( *((_QWORD *)&pvFindPara + 1) )
    LocalFree(*((HLOCAL *)&pvFindPara + 1));
  if ( !CertCloseStore(v8, 2u) )
    return GetLastError();
  return v16;
}

```

## disassembly

```asm
0x180024a24  mov     [rsp-40h+arg_10], r8
0x180024a29  push    rbp
0x180024a2a  push    rbx
0x180024a2b  push    rsi
0x180024a2c  push    rdi
0x180024a2d  push    r12
0x180024a2f  push    r13
0x180024a31  push    r14
0x180024a33  push    r15
0x180024a35  mov     rbp, rsp
0x180024a38  sub     rsp, 48h
0x180024a3c  mov     r12, rcx
0x180024a3f  xorps   xmm0, xmm0
0x180024a42  xor     ecx, ecx
0x180024a44  mov     r14, r9
0x180024a47  mov     dword ptr [rbp+arg_10], ecx
0x180024a4a  mov     r13d, ecx
0x180024a4d  movups  [rbp+pvFindPara], xmm0
0x180024a51  test    r12, r12
0x180024a54  jz      loc_180024CA1
0x180024a5a  test    r9, r9
0x180024a5d  jz      loc_180024CA1
0x180024a63  mov     rbx, [rbp+arg_20]
0x180024a67  test    rbx, rbx
0x180024a6a  jz      loc_180024CA1
0x180024a70  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180024a74  mov     rax, rdi
0x180024a77  inc     rax
0x180024a7a  cmp     [rbx+rax*2], cx
0x180024a7e  jnz     short loc_180024A77
0x180024a80  mov     r15, [rbp+arg_28]
0x180024a84  lea     r8, [rbp+arg_10]
0x180024a88  add     eax, eax
0x180024a8a  mov     r9, rbx
0x180024a8d  mov     edx, 80h
0x180024a92  mov     dword ptr [rsp+48h+pvPara], eax
0x180024a96  lea     rcx, [r15+8]
0x180024a9a  call    cs:__imp_RtlUnicodeToUTF8N
0x180024aa0  mov     esi, eax
0x180024aa2  test    eax, eax
0x180024aa4  jns     short loc_180024AEA
0x180024aa6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180024aad  lea     rax, WPP_GLOBAL_Control
0x180024ab4  cmp     rcx, rax
0x180024ab7  jz      short loc_180024ADB
0x180024ab9  test    byte ptr [rcx+1Ch], 2
0x180024abd  jz      short loc_180024ADB
0x180024abf  cmp     byte ptr [rcx+19h], 1
0x180024ac3  jb      short loc_180024ADB
0x180024ac5  mov     r9d, dword ptr [rbp+arg_10]
0x180024ac9  mov     edx, 31h ; '1'
0x180024ace  mov     rcx, [rcx+10h]
0x180024ad2  mov     dword ptr [rsp+48h+pvPara], esi
0x180024ad6  call    WPP_SF_dd
0x180024adb  mov     ecx, esi; Status
0x180024add  call    cs:__imp_RtlNtStatusToDosError
0x180024ae3  mov     ebx, eax
0x180024ae5  jmp     loc_180024CA6
0x180024aea  xor     r8d, r8d; hCryptProv
0x180024aed  mov     [rsp+48h+pvPara], rbx; pvPara
0x180024af2  mov     r9d, 28000h; dwFlags
0x180024af8  mov     edx, 10001h; dwEncodingType
0x180024afd  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180024b01  call    cs:__imp_CertOpenStore
0x180024b07  xor     esi, esi
0x180024b09  mov     r13, rax
0x180024b0c  test    rax, rax
0x180024b0f  jnz     short loc_180024B19
0x180024b11  call    cs:__imp_GetLastError
0x180024b17  jmp     short loc_180024AE3
0x180024b19  lea     rdx, [rbp+pvFindPara]; pcbBinary
0x180024b1d  mov     rcx, r14; pszString
0x180024b20  call    LmConvertCryptStringToBinary
0x180024b25  mov     ebx, eax
0x180024b27  test    eax, eax
0x180024b29  jz      short loc_180024B73
0x180024b2b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180024b32  lea     rax, WPP_GLOBAL_Control
0x180024b39  cmp     rcx, rax
0x180024b3c  jz      loc_180024CA6
0x180024b42  test    byte ptr [rcx+1Ch], 2
0x180024b46  jz      loc_180024CA6
0x180024b4c  cmp     byte ptr [rcx+19h], 1
0x180024b50  jb      loc_180024CA6
0x180024b56  mov     edx, 32h ; '2'
0x180024b5b  mov     rcx, [rcx+10h]
0x180024b5f  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x180024b66  mov     r9d, ebx
0x180024b69  call    WPP_SF_d
0x180024b6e  jmp     loc_180024CA6
0x180024b73  mov     r9d, 10000h; dwFindType
0x180024b79  mov     [rsp+48h+pPrevCertContext], rsi; pPrevCertContext
0x180024b7e  lea     rax, [rbp+pvFindPara]
0x180024b82  xor     r8d, r8d; dwFindFlags
0x180024b85  mov     rcx, r13; hCertStore
0x180024b88  mov     [rsp+48h+pvPara], rax; pvFindPara
0x180024b8d  lea     edx, [r9+1]; dwCertEncodingType
0x180024b91  call    cs:__imp_CertFindCertificateInStore
0x180024b97  mov     r14, rax
0x180024b9a  test    rax, rax
0x180024b9d  jz      loc_180024C70
0x180024ba3  lea     rsi, [r15+8Ch]
0x180024baa  xor     eax, eax
0x180024bac  inc     rdi
0x180024baf  cmp     [r12+rdi*2], ax
0x180024bb4  jnz     short loc_180024BAC
0x180024bb6  lea     eax, [rdi+rdi]
0x180024bb9  mov     r9, r12
0x180024bbc  lea     r8, [rbp+arg_10]
0x180024bc0  mov     dword ptr [rsp+48h+pvPara], eax
0x180024bc4  mov     edx, 100h
0x180024bc9  mov     rcx, rsi
0x180024bcc  call    cs:__imp_RtlUnicodeToUTF8N
0x180024bd2  mov     edi, eax
0x180024bd4  test    eax, eax
0x180024bd6  jns     short loc_180024C19
0x180024bd8  mov     ecx, eax; Status
0x180024bda  call    cs:__imp_RtlNtStatusToDosError
0x180024be0  mov     ebx, eax
0x180024be2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180024be9  lea     rax, WPP_GLOBAL_Control
0x180024bf0  cmp     rcx, rax
0x180024bf3  jz      short loc_180024C65
0x180024bf5  test    byte ptr [rcx+1Ch], 2
0x180024bf9  jz      short loc_180024C65
0x180024bfb  cmp     byte ptr [rcx+19h], 1
0x180024bff  jb      short loc_180024C65
0x180024c01  mov     r9d, dword ptr [rbp+arg_10]
0x180024c05  mov     edx, 33h ; '3'
0x180024c0a  mov     rcx, [rcx+10h]
0x180024c0e  mov     dword ptr [rsp+48h+pvPara], edi
0x180024c12  call    WPP_SF_dd
0x180024c17  jmp     short loc_180024C65
0x180024c19  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180024c20  lea     rax, WPP_GLOBAL_Control
0x180024c27  cmp     rcx, rax
0x180024c2a  jz      short loc_180024C44
0x180024c2c  test    byte ptr [rcx+1Ch], 2
0x180024c30  jz      short loc_180024C44
0x180024c32  cmp     byte ptr [rcx+19h], 2
0x180024c36  jb      short loc_180024C44
0x180024c38  mov     rcx, [rcx+10h]
0x180024c3c  mov     r9, rsi
0x180024c3f  call    WPP_SF_s
0x180024c44  mov     ecx, dword ptr [rbp+arg_10]
0x180024c47  mov     r8d, dword ptr [rbp+pvFindPara]; Size
0x180024c4b  inc     rcx
0x180024c4e  mov     rdx, qword ptr [rbp+pvFindPara+8]; Src
0x180024c52  add     rcx, rsi; void *
0x180024c55  call    memcpy_0
0x180024c5a  add     dword ptr [r15+88h], 114h
0x180024c65  mov     rcx, r14; pCertContext
0x180024c68  call    cs:__imp_CertFreeCertificateContext
0x180024c6e  jmp     short loc_180024CA6
0x180024c70  call    cs:__imp_GetLastError
0x180024c76  mov     ebx, eax
0x180024c78  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180024c7f  lea     rax, WPP_GLOBAL_Control
0x180024c86  cmp     rcx, rax
0x180024c89  jz      short loc_180024CA6
0x180024c8b  test    byte ptr [rcx+1Ch], 2
0x180024c8f  jz      short loc_180024CA6
0x180024c91  cmp     byte ptr [rcx+19h], 1
0x180024c95  jb      short loc_180024CA6
0x180024c97  mov     edx, 35h ; '5'
0x180024c9c  jmp     loc_180024B5B
0x180024ca1  mov     ebx, 57h ; 'W'
0x180024ca6  mov     rcx, qword ptr [rbp+pvFindPara+8]; hMem
0x180024caa  test    rcx, rcx
0x180024cad  jz      short loc_180024CB5
0x180024caf  call    cs:__imp_LocalFree
0x180024cb5  mov     edx, 2; dwFlags
0x180024cba  mov     rcx, r13; hCertStore
0x180024cbd  call    cs:__imp_CertCloseStore
0x180024cc3  test    eax, eax
0x180024cc5  jnz     short loc_180024CCF
0x180024cc7  call    cs:__imp_GetLastError
0x180024ccd  mov     ebx, eax
0x180024ccf  mov     eax, ebx
0x180024cd1  add     rsp, 48h
0x180024cd5  pop     r15
0x180024cd7  pop     r14
0x180024cd9  pop     r13
0x180024cdb  pop     r12
0x180024cdd  pop     rdi
0x180024cde  pop     rsi
0x180024cdf  pop     rbx
0x180024ce0  pop     rbp
0x180024ce1  retn
```
