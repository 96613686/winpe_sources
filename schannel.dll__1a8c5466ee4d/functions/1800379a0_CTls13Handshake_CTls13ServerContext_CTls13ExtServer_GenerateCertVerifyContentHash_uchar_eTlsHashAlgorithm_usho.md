# CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::GenerateCertVerifyContentHash(uchar,_eTlsHashAlgorithm,ushort const *,uchar *,ulong,ulong *)

- ea: `0x1800379a0`
- end: `0x180037d63`
- name: `?GenerateCertVerifyContentHash@?$CTls13Handshake@VCTls13ServerContext@@VCTls13ExtServer@@@@QEAAKEW4_eTlsHashAlgorithm@@PEBGPEAEKPEAK@Z`
- size: `963`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180038dd4`
- `0x18007f470`

## callees

- `0x1800379a0`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800379ca`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800379ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037d0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037d0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037cf5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037cf5`
- `ncrypt!SslComputeSessionHash` at `0x180037aa5`
- `ncrypt!SslComputeSessionHash` at `0x180037aa5`
- `bcrypt!BCryptGetProperty` at `0x180037b84`
- `bcrypt!BCryptGetProperty` at `0x180037b84`
- `bcrypt!BCryptCreateHash` at `0x180037bdb`
- `bcrypt!BCryptCreateHash` at `0x180037bdb`
- `bcrypt!BCryptHashData` at `0x180037bff`
- `bcrypt!BCryptHashData` at `0x180037c2d`
- `bcrypt!BCryptHashData` at `0x180037c4d`
- `bcrypt!BCryptHashData` at `0x180037c67`
- `bcrypt!BCryptHashData` at `0x180037bff`
- `bcrypt!BCryptHashData` at `0x180037c2d`
- `bcrypt!BCryptHashData` at `0x180037c4d`
- `bcrypt!BCryptHashData` at `0x180037c67`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008e7d2`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008e7d2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008e7a2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008e7a2`
- `bcrypt!BCryptFinishHash` at `0x180037c80`
- `bcrypt!BCryptFinishHash` at `0x180037c80`
- `bcrypt!BCryptDestroyHash` at `0x180037c99`
- `bcrypt!BCryptDestroyHash` at `0x180037c99`

## pseudocode

```c
NTSTATUS __fastcall CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::GenerateCertVerifyContentHash(
        __int64 a1,
        char a2,
        int a3,
        const wchar_t *a4,
        PUCHAR pbInput,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned __int8 v10; // al
  unsigned int *v11; // r12
  unsigned __int8 v12; // al
  PUCHAR v13; // r13
  unsigned int v14; // r14d
  unsigned int v15; // ecx
  __int64 v16; // rbx
  unsigned __int16 *v17; // rcx
  unsigned int v18; // ebx
  __int64 v19; // rax
  __int64 *v20; // rcx
  __int64 v21; // rcx
  NTSTATUS result; // eax
  int v23; // esi
  unsigned int i; // eax
  __int64 v25; // rdx
  BCRYPT_ALG_HANDLE v26; // rax
  __int64 v27; // rcx
  BCRYPT_HANDLE v28; // rbx
  ULONG v29; // edi
  UCHAR *v30; // rax
  UCHAR *v31; // rsi
  NTSTATUS v32; // ebx
  UCHAR *v33; // rdx
  ULONG cbInput; // [rsp+40h] [rbp-38h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-34h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+48h] [rbp-30h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-28h] BYREF
  ULONG pbOutput; // [rsp+B8h] [rbp+40h] BYREF

  if ( a4 )
    v10 = wcsnlen(a4, 0x40u);
  else
    v10 = 0;
  if ( v10 >= 0x40u )
    return 87;
  v11 = a7;
  if ( !a7 )
    return 87;
  if ( v10 )
    v12 = 2 * (v10 + 1);
  else
    v12 = 0;
  v13 = pbInput;
  v14 = v12;
  v15 = v12 + 64;
  *a7 = v15;
  if ( !v13 || a6 < v15 )
    return 122;
  *v11 = 0;
  if ( a4 )
  {
    v16 = v12;
    memcpy_0(v13, a4, v12);
    v13 += v16;
    *v11 = v14;
  }
  v17 = *(unsigned __int16 **)(a1 + 8);
  cbInput = 0;
  v18 = v17[17];
  v19 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)v17 + 576LL))(v17, 0);
  v20 = *(__int64 **)(*(_QWORD *)(a1 + 8) + 8LL);
  if ( v20 )
    v21 = *v20;
  else
    v21 = 0;
  result = SslComputeSessionHash(v21, v19, v18, v13, 64, &cbInput, 0);
  if ( !result )
  {
    v23 = g_dwHashInfoTotalCount;
    hObject = 0;
    for ( i = 0; i < g_dwHashInfoTotalCount; ++i )
    {
      v25 = g_pHashInfo[i];
      if ( v25 && *(_DWORD *)(v25 + 20) == a3 )
      {
        v23 = i;
        break;
      }
    }
    if ( v23 < 0 || v23 >= g_dwHashInfoTotalCount )
    {
      v23 = 0;
    }
    else
    {
      if ( v23 == 1 )
      {
        v26 = g_hMD5Provider;
        goto LABEL_25;
      }
      if ( v23 == 2 )
      {
        v26 = g_hSHAProvider;
        goto LABEL_25;
      }
    }
    v26 = (BCRYPT_ALG_HANDLE)qword_1800AE610[v23];
LABEL_25:
    hObject = v26;
    if ( v23 >= (unsigned int)g_dwHashInfoTotalCount )
      return 1168;
    _mm_lfence();
    v27 = g_pHashInfo[v23];
    if ( !v27 )
      return 1168;
    v28 = hObject;
    v29 = *(_DWORD *)(v27 + 8);
    if ( !hObject )
    {
      if ( !*(_QWORD *)v27 )
        return 1359;
      result = BCryptOpenAlgorithmProvider(&hObject, *(LPCWSTR *)v27, 0, 0);
      if ( result )
        return result;
      v28 = (BCRYPT_HANDLE)_InterlockedCompareExchange64(
                             (volatile signed __int64 *)&_ImageBase[4 * v23 + 357128],
                             (signed __int64)hObject,
                             0);
      if ( v28 )
      {
        BCryptCloseAlgorithmProvider(hObject, 0);
        hObject = v28;
      }
      else
      {
        v28 = hObject;
      }
    }
    if ( v29 <= 0x40 )
    {
      pbOutput = 0;
      pcbResult = 0;
      result = BCryptGetProperty(v28, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
      if ( !result )
      {
        if ( LsaTable )
          v30 = (UCHAR *)(*(__int64 (__fastcall **)(_QWORD))(LsaTable + 40))(pbOutput);
        else
          v30 = (UCHAR *)LocalAlloc(0x40u, pbOutput);
        v31 = v30;
        if ( v30 )
        {
          phHash = 0;
          v32 = BCryptCreateHash(v28, &phHash, v30, pbOutput, 0, 0, 0);
          if ( !v32 )
          {
            v32 = BCryptHashData(
                    phHash,
                    (PUCHAR)"                                                                TLS 1.3, ",
                    0x49u,
                    0);
            if ( !v32 )
            {
              v33 = a2 ? (UCHAR *)"server" : (UCHAR *)"client";
              v32 = BCryptHashData(phHash, v33, 6u, 0);
              if ( !v32 )
              {
                v32 = BCryptHashData(phHash, (PUCHAR)" CertificateVerify", 0x13u, 0);
                if ( !v32 )
                {
                  v32 = BCryptHashData(phHash, v13, cbInput, 0);
                  if ( !v32 )
                  {
                    v32 = BCryptFinishHash(phHash, v13, v29, 0);
                    if ( !v32 )
                      *v11 += v29;
                  }
                }
              }
            }
          }
          if ( phHash )
            BCryptDestroyHash(phHash);
          if ( LsaTable )
            (*(void (__fastcall **)(UCHAR *))(LsaTable + 48))(v31);
          else
            LocalFree(v31);
          return v32;
        }
        else
        {
          return 14;
        }
      }
      return result;
    }
    return 1359;
  }
  return result;
}

```

## disassembly

```asm
0x1800379a0  mov     [rsp-20h+arg_8], dl
0x1800379a4  push    rbp
0x1800379a5  push    rsi
0x1800379a6  push    rdi
0x1800379a7  push    r15
0x1800379a9  mov     rbp, rsp
0x1800379ac  sub     rsp, 78h
0x1800379b0  mov     rsi, r9
0x1800379b3  mov     edi, r8d
0x1800379b6  mov     r15, rcx
0x1800379b9  test    r9, r9
0x1800379bc  jz      loc_180037CE6
0x1800379c2  mov     edx, 40h ; '@'; MaxCount
0x1800379c7  mov     rcx, r9; Source
0x1800379ca  call    cs:__imp_wcsnlen
0x1800379d0  mov     [rsp+78h+var_8], r12
0x1800379d5  cmp     al, 40h ; '@'
0x1800379d7  jnb     loc_180037D59
0x1800379dd  mov     r12, [rbp+arg_30]
0x1800379e1  test    r12, r12
0x1800379e4  jz      loc_180037D59
0x1800379ea  mov     [rsp+78h+var_10], r13
0x1800379ef  mov     [rsp+78h+var_18], r14
0x1800379f4  test    al, al
0x1800379f6  jz      loc_180037D1E
0x1800379fc  inc     al
0x1800379fe  add     al, al
0x180037a00  mov     r13, [rbp+pbInput]
0x180037a04  movzx   r14d, al
0x180037a08  lea     ecx, [r14+40h]
0x180037a0c  mov     [r12], ecx
0x180037a10  test    r13, r13
0x180037a13  jz      loc_180037D4F
0x180037a19  cmp     [rbp+arg_28], ecx
0x180037a1c  jb      loc_180037D4F
0x180037a22  mov     [rsp+78h+arg_0], rbx
0x180037a2a  mov     dword ptr [r12], 0
0x180037a32  test    rsi, rsi
0x180037a35  jz      short loc_180037A4F
0x180037a37  movzx   ebx, al
0x180037a3a  mov     rdx, rsi; Src
0x180037a3d  mov     r8d, ebx; Size
0x180037a40  mov     rcx, r13; void *
0x180037a43  call    memcpy_0
0x180037a48  add     r13, rbx
0x180037a4b  mov     [r12], r14d
0x180037a4f  mov     rcx, [r15+8]
0x180037a53  xor     edx, edx
0x180037a55  mov     [rbp+cbInput], 0
0x180037a5c  mov     rax, [rcx]
0x180037a5f  movzx   ebx, word ptr [rcx+22h]
0x180037a63  mov     rax, [rax+240h]
0x180037a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a6f  mov     rcx, [r15+8]
0x180037a73  xor     r15d, r15d
0x180037a76  mov     rcx, [rcx+8]
0x180037a7a  test    rcx, rcx
0x180037a7d  jz      loc_180037D07
0x180037a83  mov     rcx, [rcx]
0x180037a86  lea     rdx, [rbp+cbInput]
0x180037a8a  mov     [rsp+78h+var_48], r15d
0x180037a8f  mov     qword ptr [rsp+78h+dwFlags], rdx
0x180037a94  mov     r9, r13
0x180037a97  mov     rdx, rax
0x180037a9a  mov     dword ptr [rsp+78h+pcbResult], 40h ; '@'
0x180037aa2  mov     r8d, ebx
0x180037aa5  call    cs:__imp_SslComputeSessionHash
0x180037aab  test    eax, eax
0x180037aad  jnz     loc_180037CB9
0x180037ab3  mov     r8d, cs:g_dwHashInfoTotalCount
0x180037aba  lea     r14, __ImageBase
0x180037ac1  mov     esi, r8d
0x180037ac4  mov     [rbp+hObject], r15
0x180037ac8  mov     eax, r15d
0x180037acb  nop     dword ptr [rax+rax+00h]
0x180037ad0  cmp     eax, r8d
0x180037ad3  jnb     short loc_180037AEF
0x180037ad5  mov     ecx, eax
0x180037ad7  mov     rdx, rva g_pHashInfo[r14+rcx*8]
0x180037adf  test    rdx, rdx
0x180037ae2  jz      short loc_180037AE9
0x180037ae4  cmp     [rdx+14h], edi
0x180037ae7  jz      short loc_180037AED
0x180037ae9  inc     eax
0x180037aeb  jmp     short loc_180037AD0
0x180037aed  mov     esi, eax
0x180037aef  test    esi, esi
0x180037af1  js      loc_180037D31
0x180037af7  cmp     esi, r8d
0x180037afa  jge     loc_180037D31
0x180037b00  mov     ecx, esi
0x180037b02  sub     ecx, 1
0x180037b05  jz      loc_180037CDA
0x180037b0b  cmp     ecx, 1
0x180037b0e  jz      loc_180037D25
0x180037b14  mov     eax, esi
0x180037b16  mov     rax, rva qword_1800AE610[r14+rax*8]
0x180037b1e  mov     [rbp+hObject], rax
0x180037b22  cmp     esi, r8d
0x180037b25  jnb     loc_180037D00
0x180037b2b  lfence
0x180037b2e  mov     eax, esi
0x180037b30  mov     rcx, rva g_pHashInfo[r14+rax*8]
0x180037b38  test    rcx, rcx
0x180037b3b  jz      loc_180037D00
0x180037b41  mov     rbx, [rbp+hObject]
0x180037b45  mov     edi, [rcx+8]
0x180037b48  test    rbx, rbx
0x180037b4b  jz      loc_18008E78C
0x180037b51  cmp     edi, 40h ; '@'
0x180037b54  ja      loc_180037D39
0x180037b5a  lea     rax, [rbp+var_34]
0x180037b5e  mov     [rsp+78h+dwFlags], r15d; dwFlags
0x180037b63  mov     r9d, 4; cbOutput
0x180037b69  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180037b6e  lea     r8, [rbp+pbOutput]; pbOutput
0x180037b72  mov     [rbp+pbOutput], r15d
0x180037b76  lea     rdx, pszProperty; "ObjectLength"
0x180037b7d  mov     [rbp+var_34], r15d
0x180037b81  mov     rcx, rbx; hObject
0x180037b84  call    cs:__imp_BCryptGetProperty
0x180037b8a  test    eax, eax
0x180037b8c  jnz     loc_180037CB9
0x180037b92  mov     rax, cs:LsaTable
0x180037b99  mov     ecx, [rbp+pbOutput]
0x180037b9c  test    rax, rax
0x180037b9f  jz      loc_180037CED
0x180037ba5  mov     rax, [rax+28h]
0x180037ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bae  mov     rsi, rax
0x180037bb1  test    rax, rax
0x180037bb4  jz      loc_180037D17
0x180037bba  mov     r9d, [rbp+pbOutput]; cbHashObject
0x180037bbe  lea     rdx, [rbp+phHash]; phHash
0x180037bc2  mov     [rsp+78h+var_48], r15d; dwFlags
0x180037bc7  mov     r8, rax; pbHashObject
0x180037bca  mov     [rsp+78h+dwFlags], r15d; cbSecret
0x180037bcf  mov     rcx, rbx; hAlgorithm
0x180037bd2  mov     [rsp+78h+pcbResult], r15; pbSecret
0x180037bd7  mov     [rbp+phHash], r15
0x180037bdb  call    cs:__imp_BCryptCreateHash
0x180037be1  mov     ebx, eax
0x180037be3  test    eax, eax
0x180037be5  jnz     loc_180037C90
0x180037beb  mov     rcx, [rbp+phHash]; hHash
0x180037bef  lea     rdx, ?LabelPrefix@?1??GenerateCertVerifyContentHash@?$CTls13Handshake@VCTls13ServerContext@@VCTls13ExtServer@@@@QEAAKEW4_eTlsHashAlgorithm@@PEBGPEAEKPEAK@Z@4QBEB; "                                       "...
0x180037bf6  xor     r9d, r9d; dwFlags
0x180037bf9  mov     r8d, 49h ; 'I'; cbInput
0x180037bff  call    cs:__imp_BCryptHashData
0x180037c05  mov     ebx, eax
0x180037c07  test    eax, eax
0x180037c09  jnz     loc_180037C90
0x180037c0f  mov     rcx, [rbp+phHash]; hHash
0x180037c13  xor     r9d, r9d; dwFlags
0x180037c16  mov     r8d, 6; cbInput
0x180037c1c  cmp     [rbp+arg_8], r9b
0x180037c20  jz      loc_180037D43
0x180037c26  lea     rdx, ?LabelServer@?1??GenerateCertVerifyContentHash@?$CTls13Handshake@VCTls13ServerContext@@VCTls13ExtServer@@@@QEAAKEW4_eTlsHashAlgorithm@@PEBGPEAEKPEAK@Z@4QBEB; "server"
0x180037c2d  call    cs:__imp_BCryptHashData
0x180037c33  mov     ebx, eax
0x180037c35  test    eax, eax
0x180037c37  jnz     short loc_180037C90
0x180037c39  mov     rcx, [rbp+phHash]; hHash
0x180037c3d  lea     rdx, ?LabelSuffix@?1??GenerateCertVerifyContentHash@?$CTls13Handshake@VCTls13ServerContext@@VCTls13ExtServer@@@@QEAAKEW4_eTlsHashAlgorithm@@PEBGPEAEKPEAK@Z@4QBEB; " CertificateVerify"
0x180037c44  xor     r9d, r9d; dwFlags
0x180037c47  mov     r8d, 13h; cbInput
0x180037c4d  call    cs:__imp_BCryptHashData
0x180037c53  mov     ebx, eax
0x180037c55  test    eax, eax
0x180037c57  jnz     short loc_180037C90
0x180037c59  mov     r8d, [rbp+cbInput]; cbInput
0x180037c5d  xor     r9d, r9d; dwFlags
0x180037c60  mov     rcx, [rbp+phHash]; hHash
0x180037c64  mov     rdx, r13; pbInput
0x180037c67  call    cs:__imp_BCryptHashData
0x180037c6d  mov     ebx, eax
0x180037c6f  test    eax, eax
0x180037c71  jnz     short loc_180037C90
0x180037c73  mov     rcx, [rbp+phHash]; hHash
0x180037c77  xor     r9d, r9d; dwFlags
0x180037c7a  mov     r8d, edi; cbOutput
0x180037c7d  mov     rdx, r13; pbOutput
0x180037c80  call    cs:__imp_BCryptFinishHash
0x180037c86  mov     ebx, eax
0x180037c88  test    eax, eax
0x180037c8a  jnz     short loc_180037C90
0x180037c8c  add     [r12], edi
0x180037c90  mov     rcx, [rbp+phHash]; hHash
0x180037c94  test    rcx, rcx
0x180037c97  jz      short loc_180037C9F
0x180037c99  call    cs:__imp_BCryptDestroyHash
0x180037c9f  mov     rax, cs:LsaTable
0x180037ca6  mov     rcx, rsi; hMem
0x180037ca9  test    rax, rax
0x180037cac  jz      short loc_180037D0F
0x180037cae  mov     rax, [rax+30h]
0x180037cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cb7  mov     eax, ebx
0x180037cb9  mov     rbx, [rsp+78h+arg_0]
0x180037cc1  mov     r13, [rsp+78h+var_10]
0x180037cc6  mov     r14, [rsp+78h+var_18]
0x180037ccb  mov     r12, [rsp+78h+var_8]
0x180037cd0  add     rsp, 78h
0x180037cd4  pop     r15
0x180037cd6  pop     rdi
0x180037cd7  pop     rsi
0x180037cd8  pop     rbp
0x180037cd9  retn
0x180037cda  mov     rax, cs:?g_hMD5Provider@@3PEAXEA; void * g_hMD5Provider
0x180037ce1  jmp     loc_180037B1E
0x180037ce6  xor     eax, eax
0x180037ce8  jmp     loc_1800379D0
0x180037ced  mov     rdx, rcx; uBytes
0x180037cf0  mov     ecx, 40h ; '@'; uFlags
0x180037cf5  call    cs:__imp_LocalAlloc
0x180037cfb  jmp     loc_180037BAE
0x180037d00  mov     eax, 490h
0x180037d05  jmp     short loc_180037CB9
0x180037d07  mov     rcx, r15
0x180037d0a  jmp     loc_180037A86
0x180037d0f  call    cs:__imp_LocalFree
0x180037d15  jmp     short loc_180037CB7
0x180037d17  mov     eax, 0Eh
0x180037d1c  jmp     short loc_180037CB9
0x180037d1e  xor     al, al
0x180037d20  jmp     loc_180037A00
0x180037d25  mov     rax, cs:?g_hSHAProvider@@3PEAXEA; void * g_hSHAProvider
0x180037d2c  jmp     loc_180037B1E
0x180037d31  mov     esi, r15d
0x180037d34  jmp     loc_180037B14
0x180037d39  mov     eax, 54Fh
0x180037d3e  jmp     loc_180037CB9
0x180037d43  lea     rdx, ?LabelClient@?1??GenerateCertVerifyContentHash@?$CTls13Handshake@VCTls13ServerContext@@VCTls13ExtServer@@@@QEAAKEW4_eTlsHashAlgorithm@@PEBGPEAEKPEAK@Z@4QBEB; "client"
0x180037d4a  jmp     loc_180037C2D
0x180037d4f  mov     eax, 7Ah ; 'z'
0x180037d54  jmp     loc_180037CC1
0x180037d59  mov     eax, 57h ; 'W'
0x180037d5e  jmp     loc_180037CCB
0x18008e78c  mov     rdx, [rcx]; pszAlgId
0x18008e78f  test    rdx, rdx
0x18008e792  jz      loc_180037D39
0x18008e798  xor     r9d, r9d; dwFlags
0x18008e79b  lea     rcx, [rbp+hObject]; phAlgorithm
0x18008e79f  xor     r8d, r8d; pszImplementation
0x18008e7a2  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18008e7a8  test    eax, eax
0x18008e7aa  jnz     loc_180037CB9
0x18008e7b0  mov     rcx, [rbp+hObject]
0x18008e7b4  movsxd  rax, esi
0x18008e7b7  lea     rdx, ds:0AE610h[rax*8]
0x18008e7bf  xor     eax, eax
0x18008e7c1  lock cmpxchg [rdx+r14], rcx
0x18008e7c7  mov     rbx, rax
0x18008e7ca  jz      short loc_18008E7E1
0x18008e7cc  mov     rcx, [rbp+hObject]; hAlgorithm
0x18008e7d0  xor     edx, edx; dwFlags
0x18008e7d2  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18008e7d8  mov     [rbp+hObject], rbx
0x18008e7dc  jmp     loc_180037B51
0x18008e7e1  mov     rbx, [rbp+hObject]
0x18008e7e5  jmp     loc_180037B51
```
