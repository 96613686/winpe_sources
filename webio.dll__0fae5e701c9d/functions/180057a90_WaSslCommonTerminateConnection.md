# WaSslCommonTerminateConnection

- ea: `0x180057a90`
- end: `0x180057de1`
- name: `WaSslCommonTerminateConnection`
- size: `849`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180057a80`
- `0x18008fa10`

## callees

- `0x180013820`
- `0x180014f04`
- `0x180021e84`
- `0x180023a30`
- `0x180039e50`
- `0x180057a90`
- `0x180057ee8`
- `0x1800703f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057b16`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057b29`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057b16`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057b29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057d9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057dbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057d9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057dbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057d86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057dab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057d86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057dab`
- `CRYPT32!CertFreeCertificateContext` at `0x180057cf2`
- `CRYPT32!CertFreeCertificateContext` at `0x180057d28`
- `CRYPT32!CertFreeCertificateContext` at `0x180057cf2`
- `CRYPT32!CertFreeCertificateContext` at `0x180057d28`
- `CRYPT32!CertFreeCertificateChain` at `0x180057d10`
- `CRYPT32!CertFreeCertificateChain` at `0x180057d10`
- `SspiCli!FreeContextBuffer` at `0x180057cb6`
- `SspiCli!FreeContextBuffer` at `0x180057cd4`
- `SspiCli!FreeContextBuffer` at `0x180057dd0`
- `SspiCli!FreeContextBuffer` at `0x180057cb6`
- `SspiCli!FreeContextBuffer` at `0x180057cd4`
- `SspiCli!FreeContextBuffer` at `0x180057dd0`
- `SspiCli!DeleteSecurityContext` at `0x180057b9e`
- `SspiCli!DeleteSecurityContext` at `0x180057b9e`

## pseudocode

```c
int __fastcall WaSslCommonTerminateConnection(__int64 a1, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // rsi
  volatile signed __int32 *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  const CERT_CONTEXT *v8; // rcx
  const CERT_CHAIN_CONTEXT *v9; // rcx
  const CERT_CONTEXT *v10; // rcx
  volatile signed __int32 *v11; // rcx
  volatile signed __int32 *v12; // rcx
  __int64 v13; // rcx
  volatile signed __int32 *v14; // rcx
  __int64 v15; // rax
  void *v16; // rdi
  void *v17; // rdi
  void *v18; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v20; // rax
  __int64 v22; // [rsp+20h] [rbp-28h] BYREF
  __int64 v23[4]; // [rsp+28h] [rbp-20h] BYREF

  v3 = *(_QWORD *)(a2 + 1360);
  v23[0] = -1;
  v4 = -1;
  if ( v3 )
  {
    WaLookasideFree();
    *(_QWORD *)(a2 + 1360) = 0;
LABEL_3:
    *(_QWORD *)(a2 + 1408) = 0;
    *(_QWORD *)(a2 + 1376) = 0;
    goto LABEL_4;
  }
  if ( *(_QWORD *)(a2 + 1376) )
  {
    v22 = *(_QWORD *)(a2 + 1376);
    WxFreeHeapEx(&v22);
    goto LABEL_3;
  }
LABEL_4:
  v5 = *(volatile signed __int32 **)(a2 + 64);
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 192) = 0;
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 12, 0xFFFFFFFF) == 1 )
      WapSslDestroySslCred((LPVOID)v5);
    *(_QWORD *)(a2 + 64) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a2 + 1456));
  v6 = *(void **)(a2 + 312);
  if ( v6 )
  {
    FreeContextBuffer(v6);
    *(_QWORD *)(a2 + 312) = 0;
    *(_DWORD *)(a2 + 320) = 0;
  }
  v7 = *(void **)(a2 + 336);
  if ( v7 )
  {
    FreeContextBuffer(v7);
    *(_QWORD *)(a2 + 336) = 0;
    *(_DWORD *)(a2 + 328) = 0;
  }
  v8 = *(const CERT_CONTEXT **)(a2 + 216);
  if ( v8 )
  {
    CertFreeCertificateContext(v8);
    *(_QWORD *)(a2 + 216) = 0;
    *(_DWORD *)(a2 + 232) = 0;
  }
  v9 = *(const CERT_CHAIN_CONTEXT **)(a2 + 224);
  if ( v9 )
  {
    CertFreeCertificateChain(v9);
    *(_QWORD *)(a2 + 224) = 0;
  }
  v10 = *(const CERT_CONTEXT **)(a2 + 96);
  if ( v10 )
  {
    CertFreeCertificateContext(v10);
    *(_QWORD *)(a2 + 96) = 0;
  }
  if ( *(_BYTE *)(a2 + 104) )
  {
    WaImpersonateToken(0, v23);
    v4 = v23[0];
  }
  if ( *(_QWORD *)(a2 + 48) != -1 && *(_QWORD *)(a2 + 56) != -1 )
  {
    DeleteSecurityContext((PCtxtHandle)(a2 + 48));
    *(_QWORD *)(a2 + 56) = -1;
    *(_QWORD *)(a2 + 48) = -1;
  }
  if ( *(_BYTE *)(a2 + 104) )
  {
    WaRestoreToken((HANDLE)v4);
    *(_BYTE *)(a2 + 104) = 0;
  }
  v11 = *(volatile signed __int32 **)(a2 + 168);
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 1, 0xFFFFFFFF) == 1 )
      WapUriFreeUriObject((LPVOID)v11);
    *(_QWORD *)(a2 + 168) = 0;
  }
  v12 = *(volatile signed __int32 **)(a2 + 176);
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 1, 0xFFFFFFFF) == 1 )
      WapUriFreeUriObject((LPVOID)v12);
    *(_QWORD *)(a2 + 176) = 0;
  }
  v13 = *(_QWORD *)(a2 + 40);
  if ( v13 )
  {
    WaDereferenceDnsCache(v13);
    *(_QWORD *)(a2 + 40) = 0;
  }
  v14 = *(volatile signed __int32 **)(a2 + 72);
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 12, 0xFFFFFFFF) == 1 )
      WapSslDestroySslCred((LPVOID)v14);
    *(_QWORD *)(a2 + 72) = 0;
  }
  v15 = *(_QWORD *)(a2 + 160);
  if ( v15 )
  {
    v23[0] = *(_QWORD *)(a2 + 160);
    LODWORD(v15) = WxFreeHeapEx(v23);
  }
  v16 = *(void **)(a2 + 152);
  if ( v16 )
  {
    ProcessHeap = GetProcessHeap();
    LODWORD(v15) = HeapFree(ProcessHeap, 0, v16);
  }
  v17 = *(void **)(a2 + 136);
  if ( v17 )
  {
    v20 = GetProcessHeap();
    LODWORD(v15) = HeapFree(v20, 0, v17);
  }
  v18 = *(void **)(a2 + 120);
  if ( v18 )
    LODWORD(v15) = FreeContextBuffer(v18);
  *(_DWORD *)a2 = 1668051827;
  return v15;
}

```

## disassembly

```asm
0x180057a90  mov     [rsp+arg_0], rbx
0x180057a95  mov     [rsp+arg_10], rbp
0x180057a9a  push    rsi
0x180057a9b  push    rdi
0x180057a9c  push    r14
0x180057a9e  sub     rsp, 30h
0x180057aa2  or      r14, 0FFFFFFFFFFFFFFFFh
0x180057aa6  mov     rbx, rdx
0x180057aa9  mov     rdx, [rdx+550h]
0x180057ab0  xor     ebp, ebp
0x180057ab2  mov     [rsp+48h+var_20], r14
0x180057ab7  mov     rsi, r14
0x180057aba  test    rdx, rdx
0x180057abd  jz      loc_180057C92
0x180057ac3  call    WaLookasideFree
0x180057ac8  mov     [rbx+550h], rbp
0x180057acf  mov     [rbx+580h], rbp
0x180057ad6  mov     [rbx+560h], rbp
0x180057add  mov     rcx, [rbx+40h]; lpMem
0x180057ae1  mov     [rbx+10h], rbp
0x180057ae5  mov     [rbx+18h], rbp
0x180057ae9  mov     [rbx+8], rbp
0x180057aed  mov     [rbx+0C0h], rbp
0x180057af4  test    rcx, rcx
0x180057af7  jz      short loc_180057B0F
0x180057af9  mov     eax, r14d
0x180057afc  lock xadd [rcx+30h], eax
0x180057b01  add     eax, r14d
0x180057b04  jnz     short loc_180057B0B
0x180057b06  call    WapSslDestroySslCred
0x180057b0b  mov     [rbx+40h], rbp
0x180057b0f  lea     rcx, [rbx+4E8h]; lpCriticalSection
0x180057b16  call    cs:__imp_DeleteCriticalSection
0x180057b1d  nop     dword ptr [rax+rax+00h]
0x180057b22  lea     rcx, [rbx+5B0h]; lpCriticalSection
0x180057b29  call    cs:__imp_DeleteCriticalSection
0x180057b30  nop     dword ptr [rax+rax+00h]
0x180057b35  mov     rcx, [rbx+138h]; pvContextBuffer
0x180057b3c  test    rcx, rcx
0x180057b3f  jnz     loc_180057CB6
0x180057b45  mov     rcx, [rbx+150h]; pvContextBuffer
0x180057b4c  test    rcx, rcx
0x180057b4f  jnz     loc_180057CD4
0x180057b55  mov     rcx, [rbx+0D8h]; pCertContext
0x180057b5c  test    rcx, rcx
0x180057b5f  jnz     loc_180057CF2
0x180057b65  mov     rcx, [rbx+0E0h]; pChainContext
0x180057b6c  test    rcx, rcx
0x180057b6f  jnz     loc_180057D10
0x180057b75  mov     rcx, [rbx+60h]; pCertContext
0x180057b79  test    rcx, rcx
0x180057b7c  jnz     loc_180057D28
0x180057b82  cmp     [rbx+68h], bpl
0x180057b86  jnz     loc_180057D3D
0x180057b8c  lea     rdi, [rbx+30h]
0x180057b90  cmp     [rdi], r14
0x180057b93  jz      short loc_180057BB1
0x180057b95  cmp     [rbx+38h], r14
0x180057b99  jz      short loc_180057BB1
0x180057b9b  mov     rcx, rdi; phContext
0x180057b9e  call    cs:__imp_DeleteSecurityContext
0x180057ba5  nop     dword ptr [rax+rax+00h]
0x180057baa  mov     [rbx+38h], r14
0x180057bae  mov     [rdi], r14
0x180057bb1  cmp     [rbx+68h], bpl
0x180057bb5  jnz     loc_180057D53
0x180057bbb  mov     rcx, [rbx+0A8h]; lpMem
0x180057bc2  test    rcx, rcx
0x180057bc5  jz      short loc_180057BE0
0x180057bc7  mov     eax, r14d
0x180057bca  lock xadd [rcx+4], eax
0x180057bcf  add     eax, r14d
0x180057bd2  jnz     short loc_180057BD9
0x180057bd4  call    WapUriFreeUriObject
0x180057bd9  mov     [rbx+0A8h], rbp
0x180057be0  mov     rcx, [rbx+0B0h]; lpMem
0x180057be7  test    rcx, rcx
0x180057bea  jnz     short loc_180057C59
0x180057bec  mov     rcx, [rbx+28h]
0x180057bf0  test    rcx, rcx
0x180057bf3  jnz     loc_180057D64
0x180057bf9  mov     rcx, [rbx+48h]; lpMem
0x180057bfd  test    rcx, rcx
0x180057c00  jnz     short loc_180057C77
0x180057c02  mov     rax, [rbx+0A0h]
0x180057c09  test    rax, rax
0x180057c0c  jnz     loc_180057D72
0x180057c12  mov     rdi, [rbx+98h]
0x180057c19  test    rdi, rdi
0x180057c1c  jnz     loc_180057D86
0x180057c22  mov     rdi, [rbx+88h]
0x180057c29  test    rdi, rdi
0x180057c2c  jnz     loc_180057DAB
0x180057c32  mov     rcx, [rbx+78h]; pvContextBuffer
0x180057c36  test    rcx, rcx
0x180057c39  jnz     loc_180057DD0
0x180057c3f  mov     rbp, [rsp+48h+arg_10]
0x180057c44  mov     dword ptr [rbx], 636C7373h
0x180057c4a  mov     rbx, [rsp+48h+arg_0]
0x180057c4f  add     rsp, 30h
0x180057c53  pop     r14
0x180057c55  pop     rdi
0x180057c56  pop     rsi
0x180057c57  retn
0x180057c59  mov     eax, r14d
0x180057c5c  lock xadd [rcx+4], eax
0x180057c61  add     eax, r14d
0x180057c64  jnz     short loc_180057C6B
0x180057c66  call    WapUriFreeUriObject
0x180057c6b  mov     [rbx+0B0h], rbp
0x180057c72  jmp     loc_180057BEC
0x180057c77  mov     eax, r14d
0x180057c7a  lock xadd [rcx+30h], eax
0x180057c7f  add     eax, r14d
0x180057c82  jnz     short loc_180057C89
0x180057c84  call    WapSslDestroySslCred
0x180057c89  mov     [rbx+48h], rbp
0x180057c8d  jmp     loc_180057C02
0x180057c92  mov     rax, [rbx+560h]
0x180057c99  test    rax, rax
0x180057c9c  jz      loc_180057ADD
0x180057ca2  lea     rcx, [rsp+48h+var_28]
0x180057ca7  mov     [rsp+48h+var_28], rax
0x180057cac  call    WxFreeHeapEx
0x180057cb1  jmp     loc_180057ACF
0x180057cb6  call    cs:__imp_FreeContextBuffer
0x180057cbd  nop     dword ptr [rax+rax+00h]
0x180057cc2  mov     [rbx+138h], rbp
0x180057cc9  mov     [rbx+140h], ebp
0x180057ccf  jmp     loc_180057B45
0x180057cd4  call    cs:__imp_FreeContextBuffer
0x180057cdb  nop     dword ptr [rax+rax+00h]
0x180057ce0  mov     [rbx+150h], rbp
0x180057ce7  mov     [rbx+148h], ebp
0x180057ced  jmp     loc_180057B55
0x180057cf2  call    cs:__imp_CertFreeCertificateContext
0x180057cf9  nop     dword ptr [rax+rax+00h]
0x180057cfe  mov     [rbx+0D8h], rbp
0x180057d05  mov     [rbx+0E8h], ebp
0x180057d0b  jmp     loc_180057B65
0x180057d10  call    cs:__imp_CertFreeCertificateChain
0x180057d17  nop     dword ptr [rax+rax+00h]
0x180057d1c  mov     [rbx+0E0h], rbp
0x180057d23  jmp     loc_180057B75
0x180057d28  call    cs:__imp_CertFreeCertificateContext
0x180057d2f  nop     dword ptr [rax+rax+00h]
0x180057d34  mov     [rbx+60h], rbp
0x180057d38  jmp     loc_180057B82
0x180057d3d  lea     rdx, [rsp+48h+var_20]
0x180057d42  xor     ecx, ecx; Token
0x180057d44  call    WaImpersonateToken
0x180057d49  mov     rsi, [rsp+48h+var_20]
0x180057d4e  jmp     loc_180057B8C
0x180057d53  mov     rcx, rsi; hObject
0x180057d56  call    WaRestoreToken
0x180057d5b  mov     [rbx+68h], bpl
0x180057d5f  jmp     loc_180057BBB
0x180057d64  call    WaDereferenceDnsCache
0x180057d69  mov     [rbx+28h], rbp
0x180057d6d  jmp     loc_180057BF9
0x180057d72  lea     rcx, [rsp+48h+var_20]
0x180057d77  mov     [rsp+48h+var_20], rax
0x180057d7c  call    WxFreeHeapEx
0x180057d81  jmp     loc_180057C12
0x180057d86  call    cs:__imp_GetProcessHeap
0x180057d8d  nop     dword ptr [rax+rax+00h]
0x180057d92  mov     r8, rdi; lpMem
0x180057d95  xor     edx, edx; dwFlags
0x180057d97  mov     rcx, rax; hHeap
0x180057d9a  call    cs:__imp_HeapFree
0x180057da1  nop     dword ptr [rax+rax+00h]
0x180057da6  jmp     loc_180057C22
0x180057dab  call    cs:__imp_GetProcessHeap
0x180057db2  nop     dword ptr [rax+rax+00h]
0x180057db7  mov     r8, rdi; lpMem
0x180057dba  xor     edx, edx; dwFlags
0x180057dbc  mov     rcx, rax; hHeap
0x180057dbf  call    cs:__imp_HeapFree
0x180057dc6  nop     dword ptr [rax+rax+00h]
0x180057dcb  jmp     loc_180057C32
0x180057dd0  call    cs:__imp_FreeContextBuffer
0x180057dd7  nop     dword ptr [rax+rax+00h]
0x180057ddc  jmp     loc_180057C3F
```
