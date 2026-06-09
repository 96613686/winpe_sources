# WaHttp3TerminateConnection

- ea: `0x18007a5c0`
- end: `0x18007a86d`
- name: `WaHttp3TerminateConnection`
- size: `685`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800052bc`
- `0x180013820`
- `0x180014f04`
- `0x18002187c`
- `0x180021e84`
- `0x1800452d4`
- `0x180077c98`
- `0x180077d1c`
- `0x18007a5c0`
- `0x180097810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007a851`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007a851`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a78b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a78b`
- `CRYPT32!CertFreeCertificateContext` at `0x18007a63b`
- `CRYPT32!CertFreeCertificateContext` at `0x18007a68f`
- `CRYPT32!CertFreeCertificateContext` at `0x18007a70f`
- `CRYPT32!CertFreeCertificateContext` at `0x18007a63b`
- `CRYPT32!CertFreeCertificateContext` at `0x18007a68f`
- `CRYPT32!CertFreeCertificateContext` at `0x18007a70f`
- `CRYPT32!CertFreeCertificateChain` at `0x18007a72e`
- `CRYPT32!CertFreeCertificateChain` at `0x18007a72e`

## pseudocode

```c
void __fastcall WaHttp3TerminateConnection(__int64 a1, int a2)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rdi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  const CERT_CONTEXT *v7; // rcx
  volatile signed __int32 *v8; // rcx
  const CERT_CONTEXT *v9; // rcx
  const CERT_CHAIN_CONTEXT *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r9
  volatile signed __int32 *v13; // rcx
  __int64 v14; // rcx
  volatile signed __int32 *v15; // rcx
  volatile signed __int32 *v16; // rcx
  _QWORD v17[7]; // [rsp+40h] [rbp-38h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(v2 + 80);
  if ( v3 )
  {
    if ( (Microsoft_Windows_WebIOEnableBits & 0x40) != 0 )
      McTemplateU0pxqqxt_EventWriteTransfer(a1, a2, *(_QWORD *)(v2 + 8), 0, 8, 0, v3, 0);
    WaCloseHttpApiConnection(**(_QWORD **)(v2 + 88), *(_QWORD *)(v2 + 80));
    *(_QWORD *)(v2 + 80) = 0;
  }
  v4 = *(_QWORD *)(v2 + 184);
  *(_QWORD *)(v2 + 192) = 0;
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 32), 0xFFFFFFFF) == 1 )
    {
      CertFreeCertificateContext(*(PCCERT_CONTEXT *)(v4 + 8));
      v5 = *(_QWORD **)(v4 + 24);
      v6 = *(_QWORD *)(v4 + 16);
      *(_QWORD *)(v4 + 8) = 0;
      WaCloseHttpApiCredential(*v5, v6);
      *(_QWORD *)(v4 + 24) = 0;
      *(_DWORD *)v4 = 1684222824;
      v17[0] = v4;
      WxFreeHeapEx(v17);
    }
    *(_QWORD *)(v2 + 184) = 0;
  }
  v7 = *(const CERT_CONTEXT **)(v2 + 176);
  *(_QWORD *)(v2 + 88) = 0;
  *(_QWORD *)(v2 + 120) = 0;
  if ( v7 )
  {
    CertFreeCertificateContext(v7);
    *(_QWORD *)(v2 + 176) = 0;
  }
  if ( *(_QWORD *)(v2 + 1080) )
  {
    v17[0] = *(_QWORD *)(v2 + 1080);
    WxFreeHeapEx(v17);
    *(_QWORD *)(v2 + 1080) = 0;
  }
  if ( *(_QWORD *)(v2 + 1088) )
  {
    v17[0] = *(_QWORD *)(v2 + 1088);
    WxFreeHeapEx(v17);
    *(_QWORD *)(v2 + 1088) = 0;
  }
  v8 = *(volatile signed __int32 **)(v2 + 96);
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 1, 0xFFFFFFFF) == 1 )
      WapUriFreeUriObject((LPVOID)v8);
    *(_QWORD *)(v2 + 96) = 0;
  }
  v9 = *(const CERT_CONTEXT **)(v2 + 144);
  if ( v9 )
  {
    CertFreeCertificateContext(v9);
    *(_QWORD *)(v2 + 144) = 0;
  }
  v10 = *(const CERT_CHAIN_CONTEXT **)(v2 + 152);
  if ( v10 )
  {
    CertFreeCertificateChain(v10);
    *(_QWORD *)(v2 + 152) = 0;
  }
  v11 = *(_QWORD *)(v2 + 280);
  if ( v11 )
  {
    WaDereferenceDnsQueryResult(v11);
    *(_QWORD *)(v2 + 280) = 0;
  }
  v12 = *(_QWORD *)(v2 + 256);
  if ( v12 )
  {
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_q(1027, 99, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v12);
    CloseHandle(*(HANDLE *)(v2 + 256));
    *(_QWORD *)(v2 + 256) = 0;
  }
  v13 = *(volatile signed __int32 **)(v2 + 304);
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13, 0xFFFFFFFF) == 1 )
    {
      v17[0] = v13;
      WxFreeHeapEx(v17);
    }
    *(_QWORD *)(v2 + 304) = 0;
  }
  v14 = *(_QWORD *)(v2 + 416);
  if ( v14 )
  {
    WaDereferenceDnsCache(v14);
    *(_QWORD *)(v2 + 416) = 0;
  }
  v15 = *(volatile signed __int32 **)(v2 + 424);
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 1, 0xFFFFFFFF) == 1 )
      WapUriFreeUriObject((LPVOID)v15);
    *(_QWORD *)(v2 + 424) = 0;
  }
  v16 = *(volatile signed __int32 **)(v2 + 432);
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16, 0xFFFFFFFF) == 1 )
    {
      v17[0] = v16;
      WxFreeHeapEx(v17);
    }
    *(_QWORD *)(v2 + 432) = 0;
  }
  if ( *(_BYTE *)(v2 + 315) )
  {
    WaTpTerminateWorkItem(v2 + 352);
    *(_BYTE *)(v2 + 315) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 24));
  *(_DWORD *)v2 = 1851994984;
}

```

## disassembly

```asm
0x18007a5c0  push    rbx
0x18007a5c2  push    rbp
0x18007a5c3  push    rsi
0x18007a5c4  push    rdi
0x18007a5c5  sub     rsp, 58h
0x18007a5c9  mov     rbx, [rcx+38h]
0x18007a5cd  xor     esi, esi
0x18007a5cf  mov     rax, [rbx+50h]
0x18007a5d3  test    rax, rax
0x18007a5d6  jz      short loc_18007A616
0x18007a5d8  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 40h
0x18007a5df  jz      short loc_18007A602
0x18007a5e1  mov     r8, [rbx+8]
0x18007a5e5  xor     r9d, r9d
0x18007a5e8  mov     [rsp+78h+var_40], esi
0x18007a5ec  mov     [rsp+78h+var_48], rax
0x18007a5f1  mov     [rsp+78h+var_50], esi
0x18007a5f5  mov     [rsp+78h+var_58], 8
0x18007a5fd  call    McTemplateU0pxqqxt_EventWriteTransfer
0x18007a602  mov     rcx, [rbx+58h]
0x18007a606  mov     rdx, [rbx+50h]
0x18007a60a  mov     rcx, [rcx]
0x18007a60d  call    WaCloseHttpApiConnection
0x18007a612  mov     [rbx+50h], rsi
0x18007a616  mov     rdi, [rbx+0B8h]
0x18007a61d  or      ebp, 0FFFFFFFFh
0x18007a620  mov     [rbx+0C0h], rsi
0x18007a627  test    rdi, rdi
0x18007a62a  jz      short loc_18007A67B
0x18007a62c  mov     eax, ebp
0x18007a62e  lock xadd [rdi+20h], eax
0x18007a633  add     eax, ebp
0x18007a635  jnz     short loc_18007A674
0x18007a637  mov     rcx, [rdi+8]; pCertContext
0x18007a63b  call    cs:__imp_CertFreeCertificateContext
0x18007a642  nop     dword ptr [rax+rax+00h]
0x18007a647  mov     rcx, [rdi+18h]
0x18007a64b  mov     rdx, [rdi+10h]
0x18007a64f  mov     [rdi+8], rsi
0x18007a653  mov     rcx, [rcx]
0x18007a656  call    WaCloseHttpApiCredential
0x18007a65b  lea     rcx, [rsp+78h+var_38]
0x18007a660  mov     [rdi+18h], rsi
0x18007a664  mov     dword ptr [rdi], 64633368h
0x18007a66a  mov     [rsp+78h+var_38], rdi
0x18007a66f  call    WxFreeHeapEx
0x18007a674  mov     [rbx+0B8h], rsi
0x18007a67b  mov     rcx, [rbx+0B0h]; pCertContext
0x18007a682  mov     [rbx+58h], rsi
0x18007a686  mov     [rbx+78h], rsi
0x18007a68a  test    rcx, rcx
0x18007a68d  jz      short loc_18007A6A2
0x18007a68f  call    cs:__imp_CertFreeCertificateContext
0x18007a696  nop     dword ptr [rax+rax+00h]
0x18007a69b  mov     [rbx+0B0h], rsi
0x18007a6a2  mov     rax, [rbx+438h]
0x18007a6a9  test    rax, rax
0x18007a6ac  jz      short loc_18007A6C4
0x18007a6ae  lea     rcx, [rsp+78h+var_38]
0x18007a6b3  mov     [rsp+78h+var_38], rax
0x18007a6b8  call    WxFreeHeapEx
0x18007a6bd  mov     [rbx+438h], rsi
0x18007a6c4  mov     rax, [rbx+440h]
0x18007a6cb  test    rax, rax
0x18007a6ce  jz      short loc_18007A6E6
0x18007a6d0  lea     rcx, [rsp+78h+var_38]
0x18007a6d5  mov     [rsp+78h+var_38], rax
0x18007a6da  call    WxFreeHeapEx
0x18007a6df  mov     [rbx+440h], rsi
0x18007a6e6  mov     rcx, [rbx+60h]; lpMem
0x18007a6ea  test    rcx, rcx
0x18007a6ed  jz      short loc_18007A703
0x18007a6ef  mov     eax, ebp
0x18007a6f1  lock xadd [rcx+4], eax
0x18007a6f6  add     eax, ebp
0x18007a6f8  jnz     short loc_18007A6FF
0x18007a6fa  call    WapUriFreeUriObject
0x18007a6ff  mov     [rbx+60h], rsi
0x18007a703  mov     rcx, [rbx+90h]; pCertContext
0x18007a70a  test    rcx, rcx
0x18007a70d  jz      short loc_18007A722
0x18007a70f  call    cs:__imp_CertFreeCertificateContext
0x18007a716  nop     dword ptr [rax+rax+00h]
0x18007a71b  mov     [rbx+90h], rsi
0x18007a722  mov     rcx, [rbx+98h]; pChainContext
0x18007a729  test    rcx, rcx
0x18007a72c  jz      short loc_18007A741
0x18007a72e  call    cs:__imp_CertFreeCertificateChain
0x18007a735  nop     dword ptr [rax+rax+00h]
0x18007a73a  mov     [rbx+98h], rsi
0x18007a741  mov     rcx, [rbx+118h]
0x18007a748  test    rcx, rcx
0x18007a74b  jz      short loc_18007A759
0x18007a74d  call    WaDereferenceDnsQueryResult
0x18007a752  mov     [rbx+118h], rsi
0x18007a759  mov     r9, [rbx+100h]
0x18007a760  test    r9, r9
0x18007a763  jz      short loc_18007A79E
0x18007a765  test    byte ptr cs:xmmword_1800AD720, 8
0x18007a76c  jz      short loc_18007A784
0x18007a76e  mov     edx, 63h ; 'c'
0x18007a773  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007a77a  mov     ecx, 403h
0x18007a77f  call    WPP_SF_q
0x18007a784  mov     rcx, [rbx+100h]; hObject
0x18007a78b  call    cs:__imp_CloseHandle
0x18007a792  nop     dword ptr [rax+rax+00h]
0x18007a797  mov     [rbx+100h], rsi
0x18007a79e  mov     rcx, [rbx+130h]
0x18007a7a5  test    rcx, rcx
0x18007a7a8  jz      short loc_18007A7CA
0x18007a7aa  mov     eax, ebp
0x18007a7ac  lock xadd [rcx], eax
0x18007a7b0  add     eax, ebp
0x18007a7b2  jnz     short loc_18007A7C3
0x18007a7b4  mov     [rsp+78h+var_38], rcx
0x18007a7b9  lea     rcx, [rsp+78h+var_38]
0x18007a7be  call    WxFreeHeapEx
0x18007a7c3  mov     [rbx+130h], rsi
0x18007a7ca  mov     rcx, [rbx+1A0h]
0x18007a7d1  test    rcx, rcx
0x18007a7d4  jz      short loc_18007A7E2
0x18007a7d6  call    WaDereferenceDnsCache
0x18007a7db  mov     [rbx+1A0h], rsi
0x18007a7e2  mov     rcx, [rbx+1A8h]; lpMem
0x18007a7e9  test    rcx, rcx
0x18007a7ec  jz      short loc_18007A805
0x18007a7ee  mov     eax, ebp
0x18007a7f0  lock xadd [rcx+4], eax
0x18007a7f5  add     eax, ebp
0x18007a7f7  jnz     short loc_18007A7FE
0x18007a7f9  call    WapUriFreeUriObject
0x18007a7fe  mov     [rbx+1A8h], rsi
0x18007a805  mov     rcx, [rbx+1B0h]
0x18007a80c  test    rcx, rcx
0x18007a80f  jz      short loc_18007A831
0x18007a811  mov     eax, ebp
0x18007a813  lock xadd [rcx], eax
0x18007a817  add     eax, ebp
0x18007a819  jnz     short loc_18007A82A
0x18007a81b  mov     [rsp+78h+var_38], rcx
0x18007a820  lea     rcx, [rsp+78h+var_38]
0x18007a825  call    WxFreeHeapEx
0x18007a82a  mov     [rbx+1B0h], rsi
0x18007a831  cmp     [rbx+13Bh], sil
0x18007a838  jz      short loc_18007A84D
0x18007a83a  lea     rcx, [rbx+160h]
0x18007a841  call    WaTpTerminateWorkItem
0x18007a846  mov     [rbx+13Bh], sil
0x18007a84d  lea     rcx, [rbx+18h]; lpCriticalSection
0x18007a851  call    cs:__imp_DeleteCriticalSection
0x18007a858  nop     dword ptr [rax+rax+00h]
0x18007a85d  mov     dword ptr [rbx], 6E633368h
0x18007a863  add     rsp, 58h
0x18007a867  pop     rdi
0x18007a868  pop     rsi
0x18007a869  pop     rbp
0x18007a86a  pop     rbx
0x18007a86b  retn
```
