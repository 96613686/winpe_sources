# GetUserTokens(void * *,void * *)

- ea: `0x14004b9d8`
- end: `0x14004bbc7`
- name: `?GetUserTokens@@YAJPEAPEAX0@Z`
- size: `495`
- prototype: `__int64 __fastcall(void **, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004b6c4`

## callees

- `0x1400087c8`
- `0x14000d4d0`
- `0x14000f4f0`
- `0x14000fb58`
- `0x14002d0a0`
- `0x14002dd20`
- `0x14004b9d8`
- `0x14004beb8`
- `0x14005d2d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14004ba2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14004ba2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14004ba12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14004ba12`
- `RPCRT4!RpcRevertToSelf` at `0x14004baa7`
- `RPCRT4!RpcRevertToSelf` at `0x14004baa7`
- `RPCRT4!RpcImpersonateClient` at `0x14004bb7c`
- `RPCRT4!RpcImpersonateClient` at `0x14004bb7c`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x14004bb2d`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x14004bb2d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14004ba6f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14004ba6f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14004bada`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14004bada`
- `KERNELBASE!GetIsEdpEnabled` at `0x14004ba83`
- `KERNELBASE!GetIsEdpEnabled` at `0x14004ba83`

## pseudocode

```c
__int64 __fastcall GetUserTokens(void **a1, void **a2)
{
  HANDLE CurrentThread; // rax
  HANDLE v5; // rcx
  HANDLE v6; // rcx
  unsigned int v7; // eax
  int v8; // edx
  int LastErrorAsHResult; // ebx
  HANDLE v10; // rcx
  HANDLE v11; // rcx
  HANDLE phNewToken; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbSid[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *TokenInformation; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  _BYTE pSid[80]; // [rsp+B0h] [rbp-50h] BYREF

  TokenHandle = (HANDLE)-1LL;
  phNewToken = (HANDLE)-1LL;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    goto LABEL_20;
  v5 = TokenHandle;
  if ( TokenHandle == (HANDLE)-1LL )
    v5 = 0;
  if ( DuplicateTokenEx(v5, 0x8Fu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
  {
    if ( (unsigned int)GetIsEdpEnabled() )
    {
      v6 = phNewToken;
      if ( phNewToken == (HANDLE)-1LL )
        v6 = 0;
      SrpSetTokenEnterpriseExempt(v6);
    }
    v7 = RpcRevertToSelf();
    LastErrorAsHResult = NCoreLibrary::HResultFromWin32((NCoreLibrary *)v7, v8);
    if ( LastErrorAsHResult >= 0 )
    {
      cbSid[0] = 68;
      if ( !CreateWellKnownSid(WinMediumLabelSid, 0, pSid, cbSid) )
        goto LABEL_18;
      memset_0(&TokenInformation, 0, 0x58u);
      v10 = phNewToken;
      TokenInformation = pSid;
      v17 = 96;
      if ( phNewToken == (HANDLE)-1LL )
        v10 = 0;
      if ( SetTokenInformation(v10, TokenIntegrityLevel, &TokenInformation, 0x58u) )
      {
        v11 = phNewToken;
        if ( phNewToken == (HANDLE)-1LL )
          v11 = 0;
        LastErrorAsHResult = RemoveModernAttributes(v11);
        if ( LastErrorAsHResult >= 0 )
        {
          *a1 = (void *)NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Detach(&TokenHandle);
          *a2 = (void *)NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Detach(&phNewToken);
        }
      }
      else
      {
LABEL_18:
        LastErrorAsHResult = GetLastErrorAsHResult();
      }
      RpcImpersonateClient(0);
    }
  }
  else
  {
LABEL_20:
    LastErrorAsHResult = GetLastErrorAsHResult();
  }
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&phNewToken);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&TokenHandle);
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x14004b9d8  mov     [rsp-8+arg_10], rbx
0x14004b9dd  push    rbp
0x14004b9de  push    rsi
0x14004b9df  push    rdi
0x14004b9e0  lea     rbp, [rsp-10h]
0x14004b9e5  sub     rsp, 110h
0x14004b9ec  mov     rax, cs:__security_cookie
0x14004b9f3  xor     rax, rsp
0x14004b9f6  mov     [rbp+20h+var_20], rax
0x14004b9fa  mov     rsi, rdx
0x14004b9fd  mov     [rsp+120h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x14004ba06  mov     rdi, rcx
0x14004ba09  mov     [rsp+120h+var_F0], 0FFFFFFFFFFFFFFFFh
0x14004ba12  call    cs:__imp_GetCurrentThread
0x14004ba19  nop     dword ptr [rax+rax+00h]
0x14004ba1e  mov     edx, 0Eh; DesiredAccess
0x14004ba23  lea     r9, [rsp+120h+TokenHandle]; TokenHandle
0x14004ba28  mov     rcx, rax; ThreadHandle
0x14004ba2b  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x14004ba2f  call    cs:__imp_OpenThreadToken
0x14004ba36  nop     dword ptr [rax+rax+00h]
0x14004ba3b  test    eax, eax
0x14004ba3d  jz      loc_14004BB8A
0x14004ba43  mov     rcx, [rsp+120h+TokenHandle]
0x14004ba48  xor     eax, eax
0x14004ba4a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14004ba4e  mov     r9d, 2; ImpersonationLevel
0x14004ba54  mov     edx, 8Fh; dwDesiredAccess
0x14004ba59  cmovz   rcx, rax; hExistingToken
0x14004ba5d  lea     rax, [rsp+120h+var_F0]
0x14004ba62  mov     [rsp+120h+phNewToken], rax; phNewToken
0x14004ba67  xor     r8d, r8d; lpTokenAttributes
0x14004ba6a  mov     [rsp+120h+TokenType], r9d; TokenType
0x14004ba6f  call    cs:__imp_DuplicateTokenEx
0x14004ba76  nop     dword ptr [rax+rax+00h]
0x14004ba7b  test    eax, eax
0x14004ba7d  jz      loc_14004BB8A
0x14004ba83  call    cs:__imp_GetIsEdpEnabled
0x14004ba8a  nop     dword ptr [rax+rax+00h]
0x14004ba8f  test    eax, eax
0x14004ba91  jz      short loc_14004BAA7
0x14004ba93  mov     rcx, [rsp+120h+var_F0]
0x14004ba98  xor     eax, eax
0x14004ba9a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14004ba9e  cmovz   rcx, rax; TokenHandle
0x14004baa2  call    SrpSetTokenEnterpriseExempt
0x14004baa7  call    cs:__imp_RpcRevertToSelf
0x14004baae  nop     dword ptr [rax+rax+00h]
0x14004bab3  mov     ecx, eax; this
0x14004bab5  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x14004baba  mov     ebx, eax
0x14004babc  test    eax, eax
0x14004babe  js      loc_14004BB91
0x14004bac4  xor     edx, edx; DomainSid
0x14004bac6  mov     [rsp+120h+cbSid], 44h ; 'D'
0x14004bace  lea     r9, [rsp+120h+cbSid]; cbSid
0x14004bad3  lea     r8, [rbp+20h+pSid]; pSid
0x14004bad7  lea     ecx, [rdx+43h]; WellKnownSidType
0x14004bada  call    cs:__imp_CreateWellKnownSid
0x14004bae1  nop     dword ptr [rax+rax+00h]
0x14004bae6  test    eax, eax
0x14004bae8  jz      loc_14004BB73
0x14004baee  mov     ebx, 58h ; 'X'
0x14004baf3  lea     rcx, [rsp+120h+TokenInformation]; void *
0x14004baf8  mov     r8d, ebx; Size
0x14004bafb  xor     edx, edx; Val
0x14004bafd  call    memset_0
0x14004bb02  mov     rcx, [rsp+120h+var_F0]
0x14004bb07  lea     rax, [rbp+20h+pSid]
0x14004bb0b  mov     [rsp+120h+TokenInformation], rax
0x14004bb10  lea     r8, [rsp+120h+TokenInformation]; TokenInformation
0x14004bb15  xor     eax, eax
0x14004bb17  mov     [rsp+120h+var_C8], 60h ; '`'
0x14004bb1f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14004bb23  lea     edx, [rbx-3Fh]; TokenInformationClass
0x14004bb26  mov     r9d, ebx; TokenInformationLength
0x14004bb29  cmovz   rcx, rax; TokenHandle
0x14004bb2d  call    cs:__imp_SetTokenInformation
0x14004bb34  nop     dword ptr [rax+rax+00h]
0x14004bb39  test    eax, eax
0x14004bb3b  jz      short loc_14004BB73
0x14004bb3d  mov     rcx, [rsp+120h+var_F0]
0x14004bb42  xor     eax, eax
0x14004bb44  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14004bb48  cmovz   rcx, rax; TokenHandle
0x14004bb4c  call    ?RemoveModernAttributes@@YAJPEAX@Z; RemoveModernAttributes(void *)
0x14004bb51  mov     ebx, eax
0x14004bb53  test    eax, eax
0x14004bb55  js      short loc_14004BB7A
0x14004bb57  lea     rcx, [rsp+120h+TokenHandle]
0x14004bb5c  call    ?Detach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAPEAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Detach(void)
0x14004bb61  lea     rcx, [rsp+120h+var_F0]
0x14004bb66  mov     [rdi], rax
0x14004bb69  call    ?Detach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAPEAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Detach(void)
0x14004bb6e  mov     [rsi], rax
0x14004bb71  jmp     short loc_14004BB7A
0x14004bb73  call    GetLastErrorAsHResult
0x14004bb78  mov     ebx, eax
0x14004bb7a  xor     ecx, ecx; BindingHandle
0x14004bb7c  call    cs:__imp_RpcImpersonateClient
0x14004bb83  nop     dword ptr [rax+rax+00h]
0x14004bb88  jmp     short loc_14004BB91
0x14004bb8a  call    GetLastErrorAsHResult
0x14004bb8f  mov     ebx, eax
0x14004bb91  lea     rcx, [rsp+120h+var_F0]
0x14004bb96  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x14004bb9b  lea     rcx, [rsp+120h+TokenHandle]
0x14004bba0  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x14004bba5  mov     eax, ebx
0x14004bba7  mov     rcx, [rbp+20h+var_20]
0x14004bbab  xor     rcx, rsp; StackCookie
0x14004bbae  call    __security_check_cookie
0x14004bbb3  mov     rbx, [rsp+120h+arg_10]
0x14004bbbb  add     rsp, 110h
0x14004bbc2  pop     rdi
0x14004bbc3  pop     rsi
0x14004bbc4  pop     rbp
0x14004bbc5  retn
```
