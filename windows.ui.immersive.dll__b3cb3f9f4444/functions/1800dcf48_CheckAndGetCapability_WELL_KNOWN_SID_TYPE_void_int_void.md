# CheckAndGetCapability(WELL_KNOWN_SID_TYPE,void *,int *,void * *)

- ea: `0x1800dcf48`
- end: `0x1800dd0b5`
- name: `?CheckAndGetCapability@@YAJW4WELL_KNOWN_SID_TYPE@@PEAXPEAHPEAPEAX@Z`
- size: `365`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, void *, int *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800d0354`
- `0x1800dce4c`

## callees

- `0x18002a36c`
- `0x18002e93c`
- `0x18003d244`
- `0x1800dcf48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dd020`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dd020`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dd004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dd004`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800dcfb0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800dcfb0`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x1800dd05d`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x1800dd05d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800dd044`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800dd044`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dcf81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dcf81`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800dcfd8`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800dcfd8`

## pseudocode

```c
__int64 __fastcall CheckAndGetCapability(WELL_KNOWN_SID_TYPE WellKnownSidType, void *a2, int *a3, void **a4)
{
  void *v7; // rax
  void *v8; // rbp
  int Error; // ebx
  HRESULT v10; // edi
  void *v11; // r14
  HANDLE CurrentThread; // rax
  void *cbSid; // [rsp+58h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF
  void *v16; // [rsp+68h] [rbp+20h] BYREF

  cbSid = a2;
  if ( a4 )
    *a4 = 0;
  *a3 = 0;
  LODWORD(cbSid) = 68;
  v7 = CoTaskMemAlloc(0x44u);
  v16 = v7;
  v8 = v7;
  if ( !v7 )
  {
    Error = -2147024882;
    goto LABEL_22;
  }
  if ( CreateWellKnownSid(WellKnownSidType, 0, v7, (DWORD *)&cbSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    TokenHandle = 0;
    v10 = CoImpersonateClient();
    if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147417833 )
    {
      Error = v10;
LABEL_21:
      CAutoHandle<void *>::~CAutoHandle<void *>(&TokenHandle);
      goto LABEL_22;
    }
    v11 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
    if ( v10 >= 0 )
    {
      v11 = TokenHandle;
      CoRevertToSelf();
    }
    if ( Error < 0 )
      goto LABEL_21;
    if ( (unsigned int)CheckTokenCapability(v11, v8, a3) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_21;
    }
    if ( a4 )
    {
      v16 = 0;
      *a4 = v8;
    }
    goto LABEL_21;
  }
LABEL_22:
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v16);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800dcf48  mov     [rsp+arg_0], rbx
0x1800dcf4d  mov     [rsp+cbSid], rdx
0x1800dcf52  push    rbp
0x1800dcf53  push    rsi
0x1800dcf54  push    rdi
0x1800dcf55  push    r14
0x1800dcf57  push    r15
0x1800dcf59  sub     rsp, 20h
0x1800dcf5d  mov     rsi, r9
0x1800dcf60  mov     r15, r8
0x1800dcf63  mov     ebx, ecx
0x1800dcf65  test    r9, r9
0x1800dcf68  jz      short loc_1800DCF71
0x1800dcf6a  mov     qword ptr [r9], 0
0x1800dcf71  mov     ecx, 44h ; 'D'; cb
0x1800dcf76  mov     dword ptr [r8], 0
0x1800dcf7d  mov     dword ptr [rsp+48h+cbSid], ecx
0x1800dcf81  call    cs:__imp_CoTaskMemAlloc
0x1800dcf88  nop     dword ptr [rax+rax+00h]
0x1800dcf8d  mov     [rsp+48h+arg_18], rax
0x1800dcf92  mov     rbp, rax
0x1800dcf95  test    rax, rax
0x1800dcf98  jnz     short loc_1800DCFA4
0x1800dcf9a  mov     ebx, 8007000Eh
0x1800dcf9f  jmp     loc_1800DD097
0x1800dcfa4  lea     r9, [rsp+48h+cbSid]; cbSid
0x1800dcfa9  mov     r8, rbp; pSid
0x1800dcfac  xor     edx, edx; DomainSid
0x1800dcfae  mov     ecx, ebx; WellKnownSidType
0x1800dcfb0  call    cs:__imp_CreateWellKnownSid
0x1800dcfb7  nop     dword ptr [rax+rax+00h]
0x1800dcfbc  test    eax, eax
0x1800dcfbe  jnz     short loc_1800DCFCF
0x1800dcfc0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800dcfc5  mov     ebx, eax
0x1800dcfc7  test    eax, eax
0x1800dcfc9  js      loc_1800DD097
0x1800dcfcf  mov     [rsp+48h+TokenHandle], 0
0x1800dcfd8  call    cs:__imp_CoImpersonateClient
0x1800dcfdf  nop     dword ptr [rax+rax+00h]
0x1800dcfe4  mov     edi, eax
0x1800dcfe6  mov     eax, 80000000h
0x1800dcfeb  lea     ecx, [rdi+rax]
0x1800dcfee  test    eax, ecx
0x1800dcff0  jnz     short loc_1800DD001
0x1800dcff2  cmp     edi, 80010117h
0x1800dcff8  jz      short loc_1800DD001
0x1800dcffa  mov     ebx, edi
0x1800dcffc  jmp     loc_1800DD08D
0x1800dd001  xor     r14d, r14d
0x1800dd004  call    cs:__imp_GetCurrentThread
0x1800dd00b  nop     dword ptr [rax+rax+00h]
0x1800dd010  mov     rcx, rax; ThreadHandle
0x1800dd013  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800dd018  lea     edx, [r14+8]; DesiredAccess
0x1800dd01c  lea     r8d, [r14+1]; OpenAsSelf
0x1800dd020  call    cs:__imp_OpenThreadToken
0x1800dd027  nop     dword ptr [rax+rax+00h]
0x1800dd02c  test    eax, eax
0x1800dd02e  jz      short loc_1800DD034
0x1800dd030  xor     ebx, ebx
0x1800dd032  jmp     short loc_1800DD03B
0x1800dd034  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800dd039  mov     ebx, eax
0x1800dd03b  test    edi, edi
0x1800dd03d  js      short loc_1800DD050
0x1800dd03f  mov     r14, [rsp+48h+TokenHandle]
0x1800dd044  call    cs:__imp_CoRevertToSelf
0x1800dd04b  nop     dword ptr [rax+rax+00h]
0x1800dd050  test    ebx, ebx
0x1800dd052  js      short loc_1800DD08D
0x1800dd054  mov     r8, r15
0x1800dd057  mov     rdx, rbp
0x1800dd05a  mov     rcx, r14
0x1800dd05d  call    cs:__imp_CheckTokenCapability
0x1800dd064  nop     dword ptr [rax+rax+00h]
0x1800dd069  test    eax, eax
0x1800dd06b  jz      short loc_1800DD071
0x1800dd06d  xor     ebx, ebx
0x1800dd06f  jmp     short loc_1800DD07C
0x1800dd071  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800dd076  mov     ebx, eax
0x1800dd078  test    eax, eax
0x1800dd07a  js      short loc_1800DD08D
0x1800dd07c  test    rsi, rsi
0x1800dd07f  jz      short loc_1800DD08D
0x1800dd081  mov     [rsp+48h+arg_18], 0
0x1800dd08a  mov     [rsi], rbp
0x1800dd08d  lea     rcx, [rsp+48h+TokenHandle]
0x1800dd092  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1800dd097  lea     rcx, [rsp+48h+arg_18]
0x1800dd09c  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800dd0a1  mov     eax, ebx
0x1800dd0a3  mov     rbx, [rsp+48h+arg_0]
0x1800dd0a8  add     rsp, 20h
0x1800dd0ac  pop     r15
0x1800dd0ae  pop     r14
0x1800dd0b0  pop     rdi
0x1800dd0b1  pop     rsi
0x1800dd0b2  pop     rbp
0x1800dd0b3  retn
```
