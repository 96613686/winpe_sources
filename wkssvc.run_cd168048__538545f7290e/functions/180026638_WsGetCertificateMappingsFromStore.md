# WsGetCertificateMappingsFromStore

- ea: `0x180026638`
- end: `0x18002693f`
- name: `WsGetCertificateMappingsFromStore`
- size: `775`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180022510`
- `0x180023930`

## callees

- `0x180022a24`
- `0x180024550`
- `0x180025054`
- `0x1800250f4`
- `0x180026638`
- `0x180036191`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800266f7`
- `ntdll!RtlNtStatusToDosError` at `0x180026812`
- `ntdll!RtlNtStatusToDosError` at `0x1800266f7`
- `ntdll!RtlNtStatusToDosError` at `0x180026812`
- `ntdll!RtlUnicodeToUTF8N` at `0x1800266ae`
- `ntdll!RtlUnicodeToUTF8N` at `0x1800267fe`
- `ntdll!RtlUnicodeToUTF8N` at `0x1800266ae`
- `ntdll!RtlUnicodeToUTF8N` at `0x1800267fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002691d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002691d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800268f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800268f9`
- `CRYPT32!CertOpenStore` at `0x180026721`
- `CRYPT32!CertOpenStore` at `0x180026721`
- `CRYPT32!CertFindCertificateInStore` at `0x1800267bd`
- `CRYPT32!CertFindCertificateInStore` at `0x1800267bd`
- `CRYPT32!CertCloseStore` at `0x18002690d`
- `CRYPT32!CertCloseStore` at `0x18002690d`
- `CRYPT32!CertFreeCertificateContext` at `0x1800268a6`
- `CRYPT32!CertFreeCertificateContext` at `0x1800268a6`

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
  void *pvPara; // rbx
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
  __int128 pvFindPara; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v27; // [rsp+A0h] [rbp+58h] BYREF
  int v28; // [rsp+A4h] [rbp+5Ch]

  v28 = HIDWORD(a3);
  v27 = 0;
  v8 = 0;
  pvFindPara = 0;
  if ( a1 && a4 && (pvPara = a5) != 0 )
  {
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)a5 + v11) );
    v12 = a6;
    v13 = RtlUnicodeToUTF8N(a6 + 8, 128, &v27, a5, 2 * (int)v11);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, v14, v27, v13);
      }
      LastError = RtlNtStatusToDosError(v13);
      goto LABEL_12;
    }
    v8 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x28000u, pvPara);
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
        WPP_SF_d(v17[2], v18, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, v16);
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
        v20 = RtlUnicodeToUTF8N(v12 + 140, 256, &v27, a1, 2 * (int)v10);
        v23 = v20;
        if ( v20 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, v12 + 140);
          }
          memcpy_0((void *)(v12 + 140 + v27 + 1LL), *((const void **)&pvFindPara + 1), (unsigned int)pvFindPara);
          *(_DWORD *)(v12 + 136) += 276;
        }
        else
        {
          v16 = RtlNtStatusToDosError(v20);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, v24, v27, v23);
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
0x180026638  mov     [rsp-40h+arg_10], r8
0x18002663d  push    rbp
0x18002663e  push    rbx
0x18002663f  push    rsi
0x180026640  push    rdi
0x180026641  push    r12
0x180026643  push    r13
0x180026645  push    r14
0x180026647  push    r15
0x180026649  mov     rbp, rsp
0x18002664c  sub     rsp, 48h
0x180026650  mov     r12, rcx
0x180026653  xorps   xmm0, xmm0
0x180026656  xor     ecx, ecx
0x180026658  mov     r14, r9
0x18002665b  mov     dword ptr [rbp+arg_10], ecx
0x18002665e  mov     r13d, ecx
0x180026661  movups  [rbp+pvFindPara], xmm0
0x180026665  test    r12, r12
0x180026668  jz      loc_1800268EB
0x18002666e  test    r9, r9
0x180026671  jz      loc_1800268EB
0x180026677  mov     rbx, [rbp+arg_20]
0x18002667b  test    rbx, rbx
0x18002667e  jz      loc_1800268EB
0x180026684  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180026688  mov     rax, rdi
0x18002668b  inc     rax
0x18002668e  cmp     [rbx+rax*2], cx
0x180026692  jnz     short loc_18002668B
0x180026694  mov     r15, [rbp+arg_28]
0x180026698  lea     r8, [rbp+arg_10]
0x18002669c  add     eax, eax
0x18002669e  mov     r9, rbx
0x1800266a1  mov     edx, 80h
0x1800266a6  mov     dword ptr [rsp+48h+pvPara], eax
0x1800266aa  lea     rcx, [r15+8]
0x1800266ae  call    cs:__imp_RtlUnicodeToUTF8N
0x1800266b5  nop     dword ptr [rax+rax+00h]
0x1800266ba  mov     esi, eax
0x1800266bc  test    eax, eax
0x1800266be  jns     short loc_18002670A
0x1800266c0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800266c7  lea     rax, WPP_GLOBAL_Control
0x1800266ce  cmp     rcx, rax
0x1800266d1  jz      short loc_1800266F5
0x1800266d3  test    byte ptr [rcx+1Ch], 2
0x1800266d7  jz      short loc_1800266F5
0x1800266d9  cmp     byte ptr [rcx+19h], 1
0x1800266dd  jb      short loc_1800266F5
0x1800266df  mov     r9d, dword ptr [rbp+arg_10]
0x1800266e3  mov     edx, 31h ; '1'
0x1800266e8  mov     rcx, [rcx+10h]
0x1800266ec  mov     dword ptr [rsp+48h+pvPara], esi
0x1800266f0  call    WPP_SF_dd
0x1800266f5  mov     ecx, esi; Status
0x1800266f7  call    cs:__imp_RtlNtStatusToDosError
0x1800266fe  nop     dword ptr [rax+rax+00h]
0x180026703  mov     ebx, eax
0x180026705  jmp     loc_1800268F0
0x18002670a  xor     r8d, r8d; hCryptProv
0x18002670d  mov     [rsp+48h+pvPara], rbx; pvPara
0x180026712  mov     r9d, 28000h; dwFlags
0x180026718  mov     edx, 10001h; dwEncodingType
0x18002671d  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180026721  call    cs:__imp_CertOpenStore
0x180026728  nop     dword ptr [rax+rax+00h]
0x18002672d  xor     esi, esi
0x18002672f  mov     r13, rax
0x180026732  test    rax, rax
0x180026735  jnz     short loc_180026745
0x180026737  call    cs:__imp_GetLastError
0x18002673e  nop     dword ptr [rax+rax+00h]
0x180026743  jmp     short loc_180026703
0x180026745  lea     rdx, [rbp+pvFindPara]; pcbBinary
0x180026749  mov     rcx, r14; pszString
0x18002674c  call    LmConvertCryptStringToBinary
0x180026751  mov     ebx, eax
0x180026753  test    eax, eax
0x180026755  jz      short loc_18002679F
0x180026757  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002675e  lea     rax, WPP_GLOBAL_Control
0x180026765  cmp     rcx, rax
0x180026768  jz      loc_1800268F0
0x18002676e  test    byte ptr [rcx+1Ch], 2
0x180026772  jz      loc_1800268F0
0x180026778  cmp     byte ptr [rcx+19h], 1
0x18002677c  jb      loc_1800268F0
0x180026782  mov     edx, 32h ; '2'
0x180026787  mov     rcx, [rcx+10h]
0x18002678b  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180026792  mov     r9d, ebx
0x180026795  call    WPP_SF_d
0x18002679a  jmp     loc_1800268F0
0x18002679f  mov     r9d, 10000h; dwFindType
0x1800267a5  mov     [rsp+48h+pPrevCertContext], rsi; pPrevCertContext
0x1800267aa  lea     rax, [rbp+pvFindPara]
0x1800267ae  xor     r8d, r8d; dwFindFlags
0x1800267b1  mov     rcx, r13; hCertStore
0x1800267b4  mov     [rsp+48h+pvPara], rax; pvFindPara
0x1800267b9  lea     edx, [r9+1]; dwCertEncodingType
0x1800267bd  call    cs:__imp_CertFindCertificateInStore
0x1800267c4  nop     dword ptr [rax+rax+00h]
0x1800267c9  mov     r14, rax
0x1800267cc  test    rax, rax
0x1800267cf  jz      loc_1800268B4
0x1800267d5  lea     rsi, [r15+8Ch]
0x1800267dc  xor     eax, eax
0x1800267de  inc     rdi
0x1800267e1  cmp     [r12+rdi*2], ax
0x1800267e6  jnz     short loc_1800267DE
0x1800267e8  lea     eax, [rdi+rdi]
0x1800267eb  mov     r9, r12
0x1800267ee  lea     r8, [rbp+arg_10]
0x1800267f2  mov     dword ptr [rsp+48h+pvPara], eax
0x1800267f6  mov     edx, 100h
0x1800267fb  mov     rcx, rsi
0x1800267fe  call    cs:__imp_RtlUnicodeToUTF8N
0x180026805  nop     dword ptr [rax+rax+00h]
0x18002680a  mov     edi, eax
0x18002680c  test    eax, eax
0x18002680e  jns     short loc_180026857
0x180026810  mov     ecx, eax; Status
0x180026812  call    cs:__imp_RtlNtStatusToDosError
0x180026819  nop     dword ptr [rax+rax+00h]
0x18002681e  mov     ebx, eax
0x180026820  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180026827  lea     rax, WPP_GLOBAL_Control
0x18002682e  cmp     rcx, rax
0x180026831  jz      short loc_1800268A3
0x180026833  test    byte ptr [rcx+1Ch], 2
0x180026837  jz      short loc_1800268A3
0x180026839  cmp     byte ptr [rcx+19h], 1
0x18002683d  jb      short loc_1800268A3
0x18002683f  mov     r9d, dword ptr [rbp+arg_10]
0x180026843  mov     edx, 33h ; '3'
0x180026848  mov     rcx, [rcx+10h]
0x18002684c  mov     dword ptr [rsp+48h+pvPara], edi
0x180026850  call    WPP_SF_dd
0x180026855  jmp     short loc_1800268A3
0x180026857  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002685e  lea     rax, WPP_GLOBAL_Control
0x180026865  cmp     rcx, rax
0x180026868  jz      short loc_180026882
0x18002686a  test    byte ptr [rcx+1Ch], 2
0x18002686e  jz      short loc_180026882
0x180026870  cmp     byte ptr [rcx+19h], 2
0x180026874  jb      short loc_180026882
0x180026876  mov     rcx, [rcx+10h]
0x18002687a  mov     r9, rsi
0x18002687d  call    WPP_SF_s
0x180026882  mov     ecx, dword ptr [rbp+arg_10]
0x180026885  mov     r8d, dword ptr [rbp+pvFindPara]; Size
0x180026889  inc     rcx
0x18002688c  mov     rdx, qword ptr [rbp+pvFindPara+8]; Src
0x180026890  add     rcx, rsi; void *
0x180026893  call    memcpy_0
0x180026898  add     dword ptr [r15+88h], 114h
0x1800268a3  mov     rcx, r14; pCertContext
0x1800268a6  call    cs:__imp_CertFreeCertificateContext
0x1800268ad  nop     dword ptr [rax+rax+00h]
0x1800268b2  jmp     short loc_1800268F0
0x1800268b4  call    cs:__imp_GetLastError
0x1800268bb  nop     dword ptr [rax+rax+00h]
0x1800268c0  mov     ebx, eax
0x1800268c2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800268c9  lea     rax, WPP_GLOBAL_Control
0x1800268d0  cmp     rcx, rax
0x1800268d3  jz      short loc_1800268F0
0x1800268d5  test    byte ptr [rcx+1Ch], 2
0x1800268d9  jz      short loc_1800268F0
0x1800268db  cmp     byte ptr [rcx+19h], 1
0x1800268df  jb      short loc_1800268F0
0x1800268e1  mov     edx, 35h ; '5'
0x1800268e6  jmp     loc_180026787
0x1800268eb  mov     ebx, 57h ; 'W'
0x1800268f0  mov     rcx, qword ptr [rbp+pvFindPara+8]; hMem
0x1800268f4  test    rcx, rcx
0x1800268f7  jz      short loc_180026905
0x1800268f9  call    cs:__imp_LocalFree
0x180026900  nop     dword ptr [rax+rax+00h]
0x180026905  mov     edx, 2; dwFlags
0x18002690a  mov     rcx, r13; hCertStore
0x18002690d  call    cs:__imp_CertCloseStore
0x180026914  nop     dword ptr [rax+rax+00h]
0x180026919  test    eax, eax
0x18002691b  jnz     short loc_18002692B
0x18002691d  call    cs:__imp_GetLastError
0x180026924  nop     dword ptr [rax+rax+00h]
0x180026929  mov     ebx, eax
0x18002692b  mov     eax, ebx
0x18002692d  add     rsp, 48h
0x180026931  pop     r15
0x180026933  pop     r14
0x180026935  pop     r13
0x180026937  pop     r12
0x180026939  pop     rdi
0x18002693a  pop     rsi
0x18002693b  pop     rbx
0x18002693c  pop     rbp
0x18002693d  retn
```
