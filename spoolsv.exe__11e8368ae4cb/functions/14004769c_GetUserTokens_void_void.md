# GetUserTokens(void * *,void * *)

- ea: `0x14004769c`
- end: `0x140047856`
- name: `?GetUserTokens@@YAJPEAPEAX0@Z`
- size: `442`
- prototype: `__int64 __fastcall(void **, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400473bc`

## callees

- `0x140007bdc`
- `0x14000c880`
- `0x14000e904`
- `0x14000eb20`
- `0x14002abc0`
- `0x14002b810`
- `0x14004769c`
- `0x140047af0`
- `0x140057c50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400476ed`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400476ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400476d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400476d6`
- `RPCRT4!RpcRevertToSelf` at `0x140047753`
- `RPCRT4!RpcRevertToSelf` at `0x140047753`
- `RPCRT4!RpcImpersonateClient` at `0x140047812`
- `RPCRT4!RpcImpersonateClient` at `0x140047812`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1400477c9`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1400477c9`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140047727`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140047727`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140047780`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140047780`
- `KERNELBASE!GetIsEdpEnabled` at `0x140047735`
- `KERNELBASE!GetIsEdpEnabled` at `0x140047735`

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
0x14004769c  mov     [rsp-8+arg_10], rbx
0x1400476a1  push    rbp
0x1400476a2  push    rsi
0x1400476a3  push    rdi
0x1400476a4  lea     rbp, [rsp-10h]
0x1400476a9  sub     rsp, 110h
0x1400476b0  mov     rax, cs:__security_cookie
0x1400476b7  xor     rax, rsp
0x1400476ba  mov     [rbp+20h+var_20], rax
0x1400476be  mov     rsi, rdx
0x1400476c1  mov     [rsp+120h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1400476ca  mov     rdi, rcx
0x1400476cd  mov     [rsp+120h+var_F0], 0FFFFFFFFFFFFFFFFh
0x1400476d6  call    cs:__imp_GetCurrentThread
0x1400476dc  mov     edx, 0Eh; DesiredAccess
0x1400476e1  lea     r9, [rsp+120h+TokenHandle]; TokenHandle
0x1400476e6  mov     rcx, rax; ThreadHandle
0x1400476e9  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1400476ed  call    cs:__imp_OpenThreadToken
0x1400476f3  test    eax, eax
0x1400476f5  jz      loc_14004781A
0x1400476fb  mov     rcx, [rsp+120h+TokenHandle]
0x140047700  xor     eax, eax
0x140047702  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140047706  mov     r9d, 2; ImpersonationLevel
0x14004770c  mov     edx, 8Fh; dwDesiredAccess
0x140047711  cmovz   rcx, rax; hExistingToken
0x140047715  lea     rax, [rsp+120h+var_F0]
0x14004771a  mov     [rsp+120h+phNewToken], rax; phNewToken
0x14004771f  xor     r8d, r8d; lpTokenAttributes
0x140047722  mov     [rsp+120h+TokenType], r9d; TokenType
0x140047727  call    cs:__imp_DuplicateTokenEx
0x14004772d  test    eax, eax
0x14004772f  jz      loc_14004781A
0x140047735  call    cs:__imp_GetIsEdpEnabled
0x14004773b  test    eax, eax
0x14004773d  jz      short loc_140047753
0x14004773f  mov     rcx, [rsp+120h+var_F0]
0x140047744  xor     eax, eax
0x140047746  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14004774a  cmovz   rcx, rax; TokenHandle
0x14004774e  call    SrpSetTokenEnterpriseExempt
0x140047753  call    cs:__imp_RpcRevertToSelf
0x140047759  mov     ecx, eax; this
0x14004775b  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x140047760  mov     ebx, eax
0x140047762  test    eax, eax
0x140047764  js      loc_140047821
0x14004776a  xor     edx, edx; DomainSid
0x14004776c  mov     [rsp+120h+cbSid], 44h ; 'D'
0x140047774  lea     r9, [rsp+120h+cbSid]; cbSid
0x140047779  lea     r8, [rbp+20h+pSid]; pSid
0x14004777d  lea     ecx, [rdx+43h]; WellKnownSidType
0x140047780  call    cs:__imp_CreateWellKnownSid
0x140047786  test    eax, eax
0x140047788  jz      short loc_140047809
0x14004778a  mov     ebx, 58h ; 'X'
0x14004778f  lea     rcx, [rsp+120h+TokenInformation]; void *
0x140047794  mov     r8d, ebx; Size
0x140047797  xor     edx, edx; Val
0x140047799  call    memset_0
0x14004779e  mov     rcx, [rsp+120h+var_F0]
0x1400477a3  lea     rax, [rbp+20h+pSid]
0x1400477a7  mov     [rsp+120h+TokenInformation], rax
0x1400477ac  lea     r8, [rsp+120h+TokenInformation]; TokenInformation
0x1400477b1  xor     eax, eax
0x1400477b3  mov     [rsp+120h+var_C8], 60h ; '`'
0x1400477bb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400477bf  lea     edx, [rbx-3Fh]; TokenInformationClass
0x1400477c2  mov     r9d, ebx; TokenInformationLength
0x1400477c5  cmovz   rcx, rax; TokenHandle
0x1400477c9  call    cs:__imp_SetTokenInformation
0x1400477cf  test    eax, eax
0x1400477d1  jz      short loc_140047809
0x1400477d3  mov     rcx, [rsp+120h+var_F0]
0x1400477d8  xor     eax, eax
0x1400477da  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400477de  cmovz   rcx, rax; TokenHandle
0x1400477e2  call    ?RemoveModernAttributes@@YAJPEAX@Z; RemoveModernAttributes(void *)
0x1400477e7  mov     ebx, eax
0x1400477e9  test    eax, eax
0x1400477eb  js      short loc_140047810
0x1400477ed  lea     rcx, [rsp+120h+TokenHandle]
0x1400477f2  call    ?Detach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAPEAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Detach(void)
0x1400477f7  lea     rcx, [rsp+120h+var_F0]
0x1400477fc  mov     [rdi], rax
0x1400477ff  call    ?Detach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAPEAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Detach(void)
0x140047804  mov     [rsi], rax
0x140047807  jmp     short loc_140047810
0x140047809  call    GetLastErrorAsHResult
0x14004780e  mov     ebx, eax
0x140047810  xor     ecx, ecx; BindingHandle
0x140047812  call    cs:__imp_RpcImpersonateClient
0x140047818  jmp     short loc_140047821
0x14004781a  call    GetLastErrorAsHResult
0x14004781f  mov     ebx, eax
0x140047821  lea     rcx, [rsp+120h+var_F0]
0x140047826  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x14004782b  lea     rcx, [rsp+120h+TokenHandle]
0x140047830  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x140047835  mov     eax, ebx
0x140047837  mov     rcx, [rbp+20h+var_20]
0x14004783b  xor     rcx, rsp; StackCookie
0x14004783e  call    __security_check_cookie
0x140047843  mov     rbx, [rsp+120h+arg_10]
0x14004784b  add     rsp, 110h
0x140047852  pop     rdi
0x140047853  pop     rsi
0x140047854  pop     rbp
0x140047855  retn
```
