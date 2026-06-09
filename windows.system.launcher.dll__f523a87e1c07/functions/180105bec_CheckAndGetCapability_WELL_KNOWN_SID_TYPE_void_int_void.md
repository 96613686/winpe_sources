# CheckAndGetCapability(WELL_KNOWN_SID_TYPE,void *,int *,void * *)

- ea: `0x180105bec`
- end: `0x180105d01`
- name: `?CheckAndGetCapability@@YAJW4WELL_KNOWN_SID_TYPE@@PEAXPEAHPEAPEAX@Z`
- size: `277`
- prototype: `__int64 __fastcall(enum WELL_KNOWN_SID_TYPE, void *, int *, void **)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800509cc`
- `0x18005101c`
- `0x180051644`
- `0x1800539c0`
- `0x180085f20`

## callees

- `0x180040918`
- `0x18007334c`
- `0x1800ea2d0`
- `0x180105bec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180105c84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180105c84`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180105c99`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180105c99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180105c16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180105c16`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180105cb7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180105cb7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180105c62`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180105c62`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180105c40`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180105c40`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180105cca`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180105cca`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CheckAndGetCapability(enum WELL_KNOWN_SID_TYPE a1, void *a2, int *a3, void **a4)
{
  void *v5; // rax
  void *v6; // rbx
  int Error; // edi
  HRESULT v8; // esi
  void *v9; // rbp
  HANDLE CurrentThread; // rax
  DWORD cbSid; // [rsp+50h] [rbp+8h] BYREF
  void *v13; // [rsp+58h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+20h] BYREF

  TokenHandle = a4;
  v13 = a2;
  *a3 = 0;
  cbSid = 68;
  v5 = CoTaskMemAlloc(0x44u);
  v6 = v5;
  v13 = v5;
  if ( v5 )
  {
    if ( CreateWellKnownSid(WinCapabilityPrivateNetworkClientServerSid, 0, v5, &cbSid)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      TokenHandle = 0;
      v8 = CoImpersonateClient();
      if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147417833 )
      {
        v9 = 0;
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
          Error = 0;
        else
          Error = ResultFromKnownLastError();
        if ( v8 >= 0 )
        {
          v9 = TokenHandle;
          CoRevertToSelf();
        }
        if ( Error >= 0 )
        {
          if ( (unsigned int)CheckTokenCapability(v9, v6, a3) )
            Error = 0;
          else
            Error = ResultFromKnownLastError();
        }
      }
      else
      {
        Error = v8;
      }
      CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&TokenHandle);
    }
  }
  else
  {
    Error = -2147024882;
  }
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v13);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180105bec  mov     rax, rsp
0x180105bef  mov     [rax+20h], r9
0x180105bf3  mov     [rax+10h], rdx
0x180105bf7  mov     [rax+8], ecx
0x180105bfa  push    rbx
0x180105bfb  push    rbp
0x180105bfc  push    rsi
0x180105bfd  push    rdi
0x180105bfe  push    r14
0x180105c00  sub     rsp, 20h
0x180105c04  mov     r14, r8
0x180105c07  mov     dword ptr [r8], 0
0x180105c0e  mov     ecx, 44h ; 'D'; cb
0x180105c13  mov     [rax+8], ecx
0x180105c16  call    cs:__imp_CoTaskMemAlloc
0x180105c1c  mov     rbx, rax
0x180105c1f  mov     [rsp+48h+arg_8], rax
0x180105c24  test    rax, rax
0x180105c27  jnz     short loc_180105C33
0x180105c29  mov     edi, 8007000Eh
0x180105c2e  jmp     loc_180105CEA
0x180105c33  lea     r9, [rsp+48h+cbSid]; cbSid
0x180105c38  mov     r8, rbx; pSid
0x180105c3b  xor     edx, edx; DomainSid
0x180105c3d  lea     ecx, [rdx+57h]; WellKnownSidType
0x180105c40  call    cs:__imp_CreateWellKnownSid
0x180105c46  test    eax, eax
0x180105c48  jnz     short loc_180105C59
0x180105c4a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180105c4f  mov     edi, eax
0x180105c51  test    eax, eax
0x180105c53  js      loc_180105CEA
0x180105c59  mov     [rsp+48h+TokenHandle], 0
0x180105c62  call    cs:__imp_CoImpersonateClient
0x180105c68  mov     esi, eax
0x180105c6a  mov     eax, 80000000h
0x180105c6f  lea     ecx, [rsi+rax]
0x180105c72  test    eax, ecx
0x180105c74  jnz     short loc_180105C82
0x180105c76  cmp     esi, 80010117h
0x180105c7c  jz      short loc_180105C82
0x180105c7e  mov     edi, esi
0x180105c80  jmp     short loc_180105CDF
0x180105c82  xor     ebp, ebp
0x180105c84  call    cs:__imp_GetCurrentThread
0x180105c8a  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180105c8f  lea     edx, [rbp+8]; DesiredAccess
0x180105c92  lea     r8d, [rbp+1]; OpenAsSelf
0x180105c96  mov     rcx, rax; ThreadHandle
0x180105c99  call    cs:__imp_OpenThreadToken
0x180105c9f  test    eax, eax
0x180105ca1  jz      short loc_180105CA7
0x180105ca3  xor     edi, edi
0x180105ca5  jmp     short loc_180105CAE
0x180105ca7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180105cac  mov     edi, eax
0x180105cae  test    esi, esi
0x180105cb0  js      short loc_180105CBD
0x180105cb2  mov     rbp, [rsp+48h+TokenHandle]
0x180105cb7  call    cs:__imp_CoRevertToSelf
0x180105cbd  test    edi, edi
0x180105cbf  js      short loc_180105CDF
0x180105cc1  mov     r8, r14
0x180105cc4  mov     rdx, rbx
0x180105cc7  mov     rcx, rbp
0x180105cca  call    cs:__imp_CheckTokenCapability
0x180105cd0  test    eax, eax
0x180105cd2  jz      short loc_180105CD8
0x180105cd4  xor     edi, edi
0x180105cd6  jmp     short loc_180105CDF
0x180105cd8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180105cdd  mov     edi, eax
0x180105cdf  lea     rcx, [rsp+48h+TokenHandle]
0x180105ce4  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180105ce9  nop
0x180105cea  lea     rcx, [rsp+48h+arg_8]
0x180105cef  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180105cf4  mov     eax, edi
0x180105cf6  add     rsp, 20h
0x180105cfa  pop     r14
0x180105cfc  pop     rdi
0x180105cfd  pop     rsi
0x180105cfe  pop     rbp
0x180105cff  pop     rbx
0x180105d00  retn
```
