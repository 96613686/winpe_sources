# GetSstpConfiguration

- ea: `0x180005ea0`
- end: `0x18000615f`
- name: `GetSstpConfiguration`
- size: `703`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x180003820`
- `0x180003e10`
- `0x1800044a0`
- `0x180004c30`
- `0x180004f10`
- `0x180005ea0`
- `0x180006168`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006001`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006001`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ff1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ff1`
- `CRYPT32!CertFreeCertificateContext` at `0x180006138`
- `CRYPT32!CertFreeCertificateContext` at `0x180006138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006014`

## pseudocode

```c
__int64 __fastcall GetSstpConfiguration(__int64 a1, wchar_t *a2, __int64 a3, unsigned int *a4)
{
  const CERT_CONTEXT *v7; // rsi
  unsigned __int8 v10; // r15
  unsigned int CryptoBindingInfo; // ebx
  unsigned int CertificateFromHash; // eax
  __int64 v13; // r8
  unsigned int v14; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int8 v19; // [rsp+40h] [rbp-C0h] BYREF
  char v20; // [rsp+41h] [rbp-BFh] BYREF
  int v21; // [rsp+44h] [rbp-BCh] BYREF
  PCCERT_CONTEXT v22; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+60h] [rbp-A0h]
  _OWORD v25[2]; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v27[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v20 = 1;
  v24 = 0;
  v26 = 0;
  v21 = 2;
  v7 = 0;
  v22 = 0;
  v19 = 0;
  v23 = 0;
  memset(v25, 0, sizeof(v25));
  memset_0(v27, 0, sizeof(v27));
  if ( !a3 )
    return 87;
  *(_OWORD *)a3 = 0;
  *(_QWORD *)(a3 + 16) = 0;
  GetSstpIsHttps(a1, a4);
  GetCryptoBindingSupportedAlgoInfo(a1, &v19);
  v10 = v19;
  CryptoBindingInfo = GetCryptoBindingInfo(a1, v19, (bool *)&v20, 0, &v21, &v23, v25);
  if ( !CryptoBindingInfo )
  {
    *(_DWORD *)a3 = v20 == 0;
    if ( v21 )
    {
      *(_DWORD *)(a3 + 8) = 0;
      *(_QWORD *)(a3 + 16) = 0;
    }
    else
    {
      if ( (v10 & 1) != 0 )
        CertificateFromHash = GetCertificateFromHash(a2, 20, (__int64)&v23, &v22);
      else
        CertificateFromHash = GetCertificateFromSha256Hash(a2, 32, (__int64)v25, &v22);
      v7 = v22;
      v14 = CertificateFromHash;
      if ( CertificateFromHash || !v22 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, v13, CertificateFromHash);
        }
        if ( (_QWORD)xmmword_1800146E0 )
        {
          LOWORD(v26) = 0;
          FormatRRASErrorString(&v26, L"Unable to get Certificates from the HASH provided by the user: %d", v14);
          ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
            gSstpCfgEtwContext,
            xmmword_1800146E0,
            &v26);
        }
        *(_DWORD *)(a3 + 8) = 0;
        CryptoBindingInfo = 0;
      }
      else
      {
        ProcessHeap = GetProcessHeap();
        v16 = HeapAlloc(ProcessHeap, v14 + 8, v14 + 32);
        *(_QWORD *)(a3 + 16) = v16;
        if ( v16 )
        {
          LOBYTE(v17) = 2;
          CryptoBindingInfo = GetHashFromCertificate(v7, v17, 0, v16);
          *(_DWORD *)(a3 + 8) = CryptoBindingInfo == 0 ? 0x20 : 0;
        }
        else
        {
          CryptoBindingInfo = GetLastError();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, v18, CryptoBindingInfo);
          }
          if ( (_QWORD)xmmword_1800146E0 )
          {
            LOWORD(v26) = 0;
            FormatRRASErrorString(&v26, L"HeapAlloc failed and returned %d", CryptoBindingInfo);
            ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
              gSstpCfgEtwContext,
              xmmword_1800146E0,
              &v26);
          }
        }
      }
    }
    if ( v7 )
      CertFreeCertificateContext(v7);
  }
  return CryptoBindingInfo;
}

```

## disassembly

```asm
0x180005ea0  push    rbp
0x180005ea2  push    rbx
0x180005ea3  push    rsi
0x180005ea4  push    rdi
0x180005ea5  push    r14
0x180005ea7  push    r15
0x180005ea9  lea     rbp, [rsp-7A8h]
0x180005eb1  sub     rsp, 8A8h
0x180005eb8  mov     rax, cs:__security_cookie
0x180005ebf  xor     rax, rsp
0x180005ec2  mov     [rbp+7D0h+var_40], rax
0x180005ec9  xor     eax, eax
0x180005ecb  mov     [rsp+8D0h+var_88F], 1
0x180005ed0  xorps   xmm1, xmm1
0x180005ed3  mov     [rsp+8D0h+var_870], eax
0x180005ed7  mov     rdi, r8
0x180005eda  mov     [rbp+7D0h+var_840], eax
0x180005edd  mov     r14, rdx
0x180005ee0  mov     [rsp+8D0h+var_88C], 2
0x180005ee8  mov     rbx, rcx
0x180005eeb  xor     esi, esi
0x180005eed  xorps   xmm0, xmm0
0x180005ef0  mov     [rsp+8D0h+var_888], rsi
0x180005ef5  xor     edx, edx; Val
0x180005ef7  mov     [rsp+8D0h+var_890], sil
0x180005efc  mov     r8d, 7FCh; Size
0x180005f02  lea     rcx, [rbp+7D0h+var_83C]; void *
0x180005f06  movups  [rsp+8D0h+var_880], xmm0
0x180005f0b  mov     r15, r9
0x180005f0e  movups  [rsp+8D0h+var_868], xmm1
0x180005f13  movups  [rsp+8D0h+var_858], xmm1
0x180005f18  call    memset_0
0x180005f1d  test    rdi, rdi
0x180005f20  jnz     short loc_180005F2A
0x180005f22  lea     eax, [rsi+57h]
0x180005f25  jmp     loc_180006140
0x180005f2a  xorps   xmm0, xmm0
0x180005f2d  xor     eax, eax
0x180005f2f  movups  xmmword ptr [rdi], xmm0
0x180005f32  mov     rdx, r15
0x180005f35  mov     [rdi+10h], rax
0x180005f39  mov     rcx, rbx
0x180005f3c  call    GetSstpIsHttps
0x180005f41  lea     rdx, [rsp+8D0h+var_890]
0x180005f46  mov     rcx, rbx
0x180005f49  call    GetCryptoBindingSupportedAlgoInfo
0x180005f4e  mov     r15b, [rsp+8D0h+var_890]
0x180005f53  lea     rax, [rsp+8D0h+var_868]
0x180005f58  mov     [rsp+8D0h+var_8A0], rax
0x180005f5d  lea     r8, [rsp+8D0h+var_88F]
0x180005f62  lea     rax, [rsp+8D0h+var_880]
0x180005f67  xor     r9d, r9d
0x180005f6a  mov     [rsp+8D0h+var_8A8], rax
0x180005f6f  mov     dl, r15b
0x180005f72  lea     rax, [rsp+8D0h+var_88C]
0x180005f77  mov     rcx, rbx
0x180005f7a  mov     [rsp+8D0h+var_8B0], rax
0x180005f7f  call    GetCryptoBindingInfo
0x180005f84  mov     ebx, eax
0x180005f86  test    eax, eax
0x180005f88  jnz     loc_18000613E
0x180005f8e  xor     ecx, ecx
0x180005f90  cmp     [rsp+8D0h+var_88F], cl
0x180005f94  setz    cl
0x180005f97  mov     [rdi], ecx
0x180005f99  cmp     [rsp+8D0h+var_88C], esi
0x180005f9d  jz      short loc_180005FAB
0x180005f9f  mov     [rdi+8], esi
0x180005fa2  mov     [rdi+10h], rsi
0x180005fa6  jmp     loc_180006130
0x180005fab  lea     r9, [rsp+8D0h+var_888]
0x180005fb0  mov     rcx, r14; Source
0x180005fb3  test    r15b, 1
0x180005fb7  jz      short loc_180005FCA
0x180005fb9  lea     r8, [rsp+8D0h+var_880]
0x180005fbe  mov     edx, 14h
0x180005fc3  call    GetCertificateFromHash
0x180005fc8  jmp     short loc_180005FD9
0x180005fca  lea     r8, [rsp+8D0h+var_868]
0x180005fcf  mov     edx, 20h ; ' '
0x180005fd4  call    GetCertificateFromSha256Hash
0x180005fd9  mov     rsi, [rsp+8D0h+var_888]
0x180005fde  mov     ebx, eax
0x180005fe0  test    eax, eax
0x180005fe2  jnz     loc_1800060B6
0x180005fe8  test    rsi, rsi
0x180005feb  jz      loc_1800060B6
0x180005ff1  call    cs:__imp_GetProcessHeap
0x180005ff7  mov     rcx, rax; hHeap
0x180005ffa  lea     edx, [rbx+8]; dwFlags
0x180005ffd  lea     r8d, [rbx+20h]; dwBytes
0x180006001  call    cs:__imp_HeapAlloc
0x180006007  mov     [rdi+10h], rax
0x18000600b  test    rax, rax
0x18000600e  jnz     loc_180006096
0x180006014  call    cs:__imp_GetLastError
0x18000601a  mov     ebx, eax
0x18000601c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006023  lea     rax, WPP_GLOBAL_Control
0x18000602a  cmp     rcx, rax
0x18000602d  jz      short loc_18000604C
0x18000602f  test    byte ptr [rcx+1Ch], 40h
0x180006033  jz      short loc_18000604C
0x180006035  cmp     byte ptr [rcx+19h], 1
0x180006039  jb      short loc_18000604C
0x18000603b  mov     rcx, [rcx+10h]
0x18000603f  mov     edx, 0BDh
0x180006044  mov     r9d, ebx
0x180006047  call    WPP_SF_d
0x18000604c  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180006054  jz      loc_180006130
0x18000605a  xor     eax, eax
0x18000605c  lea     rdx, aHeapallocFaile; "HeapAlloc failed and returned %d"
0x180006063  mov     r8d, ebx
0x180006066  mov     word ptr [rbp+7D0h+var_840], ax
0x18000606a  lea     rcx, [rbp+7D0h+var_840]
0x18000606e  call    FormatRRASErrorString
0x180006073  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000607a  lea     r8, [rbp+7D0h+var_840]
0x18000607e  mov     rcx, cs:gSstpCfgEtwContext
0x180006085  mov     rax, cs:gSstpCfgTemplateFunc
0x18000608c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006091  jmp     loc_180006130
0x180006096  mov     r9, rax
0x180006099  xor     r8d, r8d
0x18000609c  mov     dl, 2
0x18000609e  mov     rcx, rsi
0x1800060a1  call    GetHashFromCertificate
0x1800060a6  mov     ebx, eax
0x1800060a8  neg     eax
0x1800060aa  sbb     ecx, ecx
0x1800060ac  not     ecx
0x1800060ae  and     ecx, 20h
0x1800060b1  mov     [rdi+8], ecx
0x1800060b4  jmp     short loc_180006130
0x1800060b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060bd  lea     rax, WPP_GLOBAL_Control
0x1800060c4  cmp     rcx, rax
0x1800060c7  jz      short loc_1800060E6
0x1800060c9  test    byte ptr [rcx+1Ch], 40h
0x1800060cd  jz      short loc_1800060E6
0x1800060cf  cmp     byte ptr [rcx+19h], 1
0x1800060d3  jb      short loc_1800060E6
0x1800060d5  mov     rcx, [rcx+10h]
0x1800060d9  mov     edx, 0BEh
0x1800060de  mov     r9d, ebx
0x1800060e1  call    WPP_SF_d
0x1800060e6  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800060ee  jz      short loc_180006127
0x1800060f0  xor     eax, eax
0x1800060f2  lea     rdx, aUnableToGetCer_4; "Unable to get Certificates from the HAS"...
0x1800060f9  mov     r8d, ebx
0x1800060fc  mov     word ptr [rbp+7D0h+var_840], ax
0x180006100  lea     rcx, [rbp+7D0h+var_840]
0x180006104  call    FormatRRASErrorString
0x180006109  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180006110  lea     r8, [rbp+7D0h+var_840]
0x180006114  mov     rcx, cs:gSstpCfgEtwContext
0x18000611b  mov     rax, cs:gSstpCfgTemplateFunc
0x180006122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006127  mov     dword ptr [rdi+8], 0
0x18000612e  xor     ebx, ebx
0x180006130  test    rsi, rsi
0x180006133  jz      short loc_18000613E
0x180006135  mov     rcx, rsi; pCertContext
0x180006138  call    cs:__imp_CertFreeCertificateContext
0x18000613e  mov     eax, ebx
0x180006140  mov     rcx, [rbp+7D0h+var_40]
0x180006147  xor     rcx, rsp; StackCookie
0x18000614a  call    __security_check_cookie
0x18000614f  add     rsp, 8A8h
0x180006156  pop     r15
0x180006158  pop     r14
0x18000615a  pop     rdi
0x18000615b  pop     rsi
0x18000615c  pop     rbx
0x18000615d  pop     rbp
0x18000615e  retn
```
