# WfpAlepCreateTokenFromLogonId

- ea: `0x14012b884`
- end: `0x14012bbd3`
- name: `WfpAlepCreateTokenFromLogonId`
- size: `847`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14012b79c`
- `0x140179110`

## callees

- `0x1400c7fe0`
- `0x14012b884`
- `0x14015081c`
- `0x1401c0fd0`

## import_xrefs

- `ksecdd!FreeContextBuffer` at `0x14012b991`
- `ksecdd!FreeContextBuffer` at `0x14012b9a6`
- `ksecdd!FreeContextBuffer` at `0x14012ba8d`
- `ksecdd!FreeContextBuffer` at `0x14012bb29`
- `ksecdd!FreeContextBuffer` at `0x14012b991`
- `ksecdd!FreeContextBuffer` at `0x14012b9a6`
- `ksecdd!FreeContextBuffer` at `0x14012ba8d`
- `ksecdd!FreeContextBuffer` at `0x14012bb29`
- `ksecdd!InitializeSecurityContextW` at `0x14012bb00`
- `ksecdd!InitializeSecurityContextW` at `0x14012bb00`
- `ksecdd!AcceptSecurityContext` at `0x14012bb7e`
- `ksecdd!AcceptSecurityContext` at `0x14012bb7e`
- `ksecdd!QuerySecurityContextToken` at `0x14012bbb7`
- `ksecdd!QuerySecurityContextToken` at `0x14012bbb7`
- `ksecdd!DeleteSecurityContext` at `0x14012b9ba`
- `ksecdd!DeleteSecurityContext` at `0x14012b9ce`
- `ksecdd!DeleteSecurityContext` at `0x14012b9ba`
- `ksecdd!DeleteSecurityContext` at `0x14012b9ce`
- `ksecdd!FreeCredentialsHandle` at `0x14012b9e3`
- `ksecdd!FreeCredentialsHandle` at `0x14012b9f8`
- `ksecdd!FreeCredentialsHandle` at `0x14012b9e3`
- `ksecdd!FreeCredentialsHandle` at `0x14012b9f8`
- `ksecdd!AcquireCredentialsHandleW` at `0x14012b95b`
- `ksecdd!AcquireCredentialsHandleW` at `0x14012ba6d`
- `ksecdd!AcquireCredentialsHandleW` at `0x14012b95b`
- `ksecdd!AcquireCredentialsHandleW` at `0x14012ba6d`

## string_xrefs

- `0x14012b967`: `WfpAlepCreateTokenFromLogonId`

## pseudocode

```c
__int64 __fastcall WfpAlepCreateTokenFromLogonId(__int64 a1, void **a2)
{
  char v2; // di
  char v4; // r15
  struct _SecHandle *p_phNewContext; // r14
  struct _SecHandle *p_phContext; // rsi
  unsigned int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rbx
  unsigned int pfContextAttr; // [rsp+60h] [rbp-A0h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+68h] [rbp-98h] BYREF
  PVOID pvContextBuffer[2]; // [rsp+70h] [rbp-90h] BYREF
  PVOID v14[2]; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING pPackage; // [rsp+90h] [rbp-70h] BYREF
  struct _SecBufferDesc v16; // [rsp+A0h] [rbp-60h] BYREF
  struct _SecBufferDesc pInput; // [rsp+B0h] [rbp-50h] BYREF
  __int64 pvLogonId; // [rsp+C0h] [rbp-40h] BYREF
  struct _SecHandle phContext; // [rsp+C8h] [rbp-38h] BYREF
  struct _SecHandle v20; // [rsp+D8h] [rbp-28h] BYREF
  struct _SecHandle phCredential; // [rsp+E8h] [rbp-18h] BYREF
  struct _SecHandle phNewContext; // [rsp+F8h] [rbp-8h] BYREF

  pvLogonId = a1;
  *(_QWORD *)&pPackage.Length = 655368;
  pfContextAttr = 0;
  ptsExpiry.QuadPart = 0;
  pPackage.Buffer = L"NTLM";
  pInput.ulVersion = 0;
  pInput.pBuffers = (PSecBuffer)v14;
  v2 = 1;
  pInput.cBuffers = 1;
  v16.pBuffers = (PSecBuffer)pvContextBuffer;
  v16.ulVersion = 0;
  v16.cBuffers = 1;
  *(_OWORD *)v14 = 0;
  v4 = 0;
  *(_OWORD *)pvContextBuffer = 0;
  p_phNewContext = 0;
  phCredential = 0;
  p_phContext = 0;
  HIDWORD(v14[0]) = 2;
  v20 = 0;
  HIDWORD(pvContextBuffer[0]) = 2;
  phNewContext = 0;
  phContext = 0;
  v7 = AcquireCredentialsHandleW(0, &pPackage, 2u, &pvLogonId, 0, 0, 0, &phCredential, &ptsExpiry);
  if ( v7 )
  {
    v2 = 0;
  }
  else
  {
    v7 = AcquireCredentialsHandleW(0, &pPackage, 1u, 0, 0, 0, 0, &v20, &ptsExpiry);
    if ( !v7 )
    {
      v4 = 1;
      while ( 1 )
      {
        if ( v14[1] )
        {
          FreeContextBuffer(v14[1]);
          LODWORD(v14[0]) = 0;
          v14[1] = 0;
        }
        v7 = InitializeSecurityContextW(
               &phCredential,
               p_phNewContext,
               0,
               0x100u,
               0,
               0x10u,
               (PSecBufferDesc)((unsigned __int64)&v16 & -(__int64)(pvContextBuffer[1] != 0)),
               0,
               &phNewContext,
               &pInput,
               &pfContextAttr,
               &ptsExpiry);
        if ( v7 )
        {
          if ( v7 != 590610 )
            break;
        }
        p_phNewContext = &phNewContext;
        if ( pvContextBuffer[1] )
        {
          FreeContextBuffer(pvContextBuffer[1]);
          LODWORD(pvContextBuffer[0]) = 0;
          pvContextBuffer[1] = 0;
        }
        v7 = AcceptSecurityContext(
               &v20,
               p_phContext,
               &pInput,
               0x100u,
               0x10u,
               &phContext,
               &v16,
               &pfContextAttr,
               &ptsExpiry);
        if ( v7 )
        {
          if ( v7 != 590610 )
            break;
        }
        p_phContext = &phContext;
        if ( v7 != 590610 )
        {
          v7 = QuerySecurityContextToken(&phContext, a2);
          if ( v7 )
            break;
          v9 = 0;
          goto LABEL_4;
        }
      }
    }
  }
  v9 = WfpReportSysErrorAsWinError(v8, "WfpAlepCreateTokenFromLogonId", v7);
LABEL_4:
  if ( pvContextBuffer[1] )
    FreeContextBuffer(pvContextBuffer[1]);
  if ( v14[1] )
    FreeContextBuffer(v14[1]);
  if ( p_phContext )
    DeleteSecurityContext(p_phContext);
  if ( p_phNewContext )
    DeleteSecurityContext(p_phNewContext);
  if ( v4 )
    FreeCredentialsHandle(&v20);
  if ( v2 )
    FreeCredentialsHandle(&phCredential);
  if ( v9 )
    WfpReportError(v9, "WfpAlepCreateTokenFromLogonId");
  return v9;
}

```

## disassembly

```asm
0x14012b884  mov     [rsp-8+arg_10], rbx
0x14012b889  push    rbp
0x14012b88a  push    rsi
0x14012b88b  push    rdi
0x14012b88c  push    r12
0x14012b88e  push    r13
0x14012b890  push    r14
0x14012b892  push    r15
0x14012b894  lea     rbp, [rsp-10h]
0x14012b899  sub     rsp, 110h
0x14012b8a0  mov     rax, cs:__security_cookie
0x14012b8a7  xor     rax, rsp
0x14012b8aa  mov     [rbp+40h+var_38], rax
0x14012b8ae  xor     r12d, r12d
0x14012b8b1  mov     [rbp+40h+pvLogonId], rcx
0x14012b8b5  xorps   xmm0, xmm0
0x14012b8b8  mov     qword ptr [rbp+40h+pPackage.Length], 0A0008h
0x14012b8c0  xorps   xmm1, xmm1
0x14012b8c3  mov     [rsp+140h+var_E0], r12d
0x14012b8c8  lea     rax, aNtlm; "NTLM"
0x14012b8cf  mov     qword ptr [rsp+140h+var_D8], r12
0x14012b8d4  mov     [rbp+40h+pPackage.Buffer], rax
0x14012b8d8  lea     r8d, [r12+2]; fCredentialUse
0x14012b8dd  lea     rax, [rbp+40h+var_C0]
0x14012b8e1  mov     [rbp+40h+pInput.ulVersion], r12d
0x14012b8e5  mov     [rbp+40h+pInput.pBuffers], rax
0x14012b8e9  lea     edi, [r12+1]
0x14012b8ee  lea     rax, [rsp+140h+pvContextBuffer]
0x14012b8f3  mov     [rbp+40h+pInput.cBuffers], edi
0x14012b8f6  mov     [rbp+40h+var_A0.pBuffers], rax
0x14012b8fa  lea     r9, [rbp+40h+pvLogonId]; pvLogonId
0x14012b8fe  lea     rax, [rsp+140h+var_D8]
0x14012b903  mov     [rbp+40h+var_A0.ulVersion], r12d
0x14012b907  mov     [rsp+140h+ptsExpiry], rax; ptsExpiry
0x14012b90c  mov     rbx, rdx
0x14012b90f  lea     rax, [rbp+40h+var_58]
0x14012b913  mov     [rbp+40h+var_A0.cBuffers], edi
0x14012b916  mov     [rsp+140h+phCredential], rax; phCredential
0x14012b91b  lea     rdx, [rbp+40h+pPackage]; pPackage
0x14012b91f  mov     [rsp+140h+pvGetKeyArgument], r12; pvGetKeyArgument
0x14012b924  xor     ecx, ecx; pPrincipal
0x14012b926  movups  xmmword ptr [rbp+40h+var_C0], xmm0
0x14012b92a  mov     [rsp+140h+pGetKeyFn], r12; pGetKeyFn
0x14012b92f  mov     r15b, r12b
0x14012b932  movups  xmmword ptr [rsp+140h+pvContextBuffer], xmm1
0x14012b937  mov     [rsp+140h+pAuthData], r12; pAuthData
0x14012b93c  mov     r14d, r12d
0x14012b93f  movups  xmmword ptr [rbp+40h+var_58.dwLower], xmm0
0x14012b943  mov     esi, r12d
0x14012b946  mov     dword ptr [rbp+40h+var_C0+4], r8d
0x14012b94a  movups  xmmword ptr [rbp+40h+var_68.dwLower], xmm1
0x14012b94e  mov     dword ptr [rsp+140h+pvContextBuffer+4], r8d
0x14012b953  movups  xmmword ptr [rbp+40h+phNewContext.dwLower], xmm0
0x14012b957  movups  xmmword ptr [rbp+40h+phContext.dwLower], xmm1
0x14012b95b  call    cs:__imp_AcquireCredentialsHandleW
0x14012b962  nop     dword ptr [rax+rax+00h]
0x14012b967  lea     r13, aWfpalepcreatet; "WfpAlepCreateTokenFromLogonId"
0x14012b96e  test    eax, eax
0x14012b970  jz      loc_14012BA3F
0x14012b976  mov     dil, r12b
0x14012b979  mov     r8d, eax
0x14012b97c  mov     rdx, r13
0x14012b97f  call    WfpReportSysErrorAsWinError
0x14012b984  mov     rbx, rax
0x14012b987  mov     rcx, [rsp+140h+pvContextBuffer+8]; pvContextBuffer
0x14012b98c  test    rcx, rcx
0x14012b98f  jz      short loc_14012B99D
0x14012b991  call    cs:__imp_FreeContextBuffer
0x14012b998  nop     dword ptr [rax+rax+00h]
0x14012b99d  mov     rcx, [rbp+40h+var_C0+8]; pvContextBuffer
0x14012b9a1  test    rcx, rcx
0x14012b9a4  jz      short loc_14012B9B2
0x14012b9a6  call    cs:__imp_FreeContextBuffer
0x14012b9ad  nop     dword ptr [rax+rax+00h]
0x14012b9b2  test    rsi, rsi
0x14012b9b5  jz      short loc_14012B9C6
0x14012b9b7  mov     rcx, rsi; phContext
0x14012b9ba  call    cs:__imp_DeleteSecurityContext
0x14012b9c1  nop     dword ptr [rax+rax+00h]
0x14012b9c6  test    r14, r14
0x14012b9c9  jz      short loc_14012B9DA
0x14012b9cb  mov     rcx, r14; phContext
0x14012b9ce  call    cs:__imp_DeleteSecurityContext
0x14012b9d5  nop     dword ptr [rax+rax+00h]
0x14012b9da  test    r15b, r15b
0x14012b9dd  jz      short loc_14012B9EF
0x14012b9df  lea     rcx, [rbp+40h+var_68]; phCredential
0x14012b9e3  call    cs:__imp_FreeCredentialsHandle
0x14012b9ea  nop     dword ptr [rax+rax+00h]
0x14012b9ef  test    dil, dil
0x14012b9f2  jz      short loc_14012BA04
0x14012b9f4  lea     rcx, [rbp+40h+var_58]; phCredential
0x14012b9f8  call    cs:__imp_FreeCredentialsHandle
0x14012b9ff  nop     dword ptr [rax+rax+00h]
0x14012ba04  test    rbx, rbx
0x14012ba07  jz      short loc_14012BA14
0x14012ba09  mov     rdx, r13
0x14012ba0c  mov     rcx, rbx
0x14012ba0f  call    WfpReportError
0x14012ba14  mov     rax, rbx
0x14012ba17  mov     rcx, [rbp+40h+var_38]
0x14012ba1b  xor     rcx, rsp; StackCookie
0x14012ba1e  call    __security_check_cookie
0x14012ba23  mov     rbx, [rsp+140h+arg_10]
0x14012ba2b  add     rsp, 110h
0x14012ba32  pop     r15
0x14012ba34  pop     r14
0x14012ba36  pop     r13
0x14012ba38  pop     r12
0x14012ba3a  pop     rdi
0x14012ba3b  pop     rsi
0x14012ba3c  pop     rbp
0x14012ba3d  retn
0x14012ba3f  lea     rax, [rsp+140h+var_D8]
0x14012ba44  xor     r9d, r9d; pvLogonId
0x14012ba47  mov     [rsp+140h+ptsExpiry], rax; ptsExpiry
0x14012ba4c  lea     rdx, [rbp+40h+pPackage]; pPackage
0x14012ba50  lea     rax, [rbp+40h+var_68]
0x14012ba54  mov     r8d, edi; fCredentialUse
0x14012ba57  mov     [rsp+140h+phCredential], rax; phCredential
0x14012ba5c  xor     ecx, ecx; pPrincipal
0x14012ba5e  mov     [rsp+140h+pvGetKeyArgument], r12; pvGetKeyArgument
0x14012ba63  mov     [rsp+140h+pGetKeyFn], r12; pGetKeyFn
0x14012ba68  mov     [rsp+140h+pAuthData], r12; pAuthData
0x14012ba6d  call    cs:__imp_AcquireCredentialsHandleW
0x14012ba74  nop     dword ptr [rax+rax+00h]
0x14012ba79  test    eax, eax
0x14012ba7b  jnz     loc_14012B979
0x14012ba81  mov     r15b, dil
0x14012ba84  mov     rcx, [rbp+40h+var_C0+8]; pvContextBuffer
0x14012ba88  test    rcx, rcx
0x14012ba8b  jz      short loc_14012BAA1
0x14012ba8d  call    cs:__imp_FreeContextBuffer
0x14012ba94  nop     dword ptr [rax+rax+00h]
0x14012ba99  mov     dword ptr [rbp+40h+var_C0], r12d
0x14012ba9d  mov     [rbp+40h+var_C0+8], r12
0x14012baa1  mov     rax, [rsp+140h+pvContextBuffer+8]
0x14012baa6  mov     r9d, 100h; fContextReq
0x14012baac  neg     rax
0x14012baaf  mov     rdx, r14; phContext
0x14012bab2  lea     rax, [rbp+40h+var_A0]
0x14012bab6  sbb     rcx, rcx
0x14012bab9  xor     r8d, r8d; pTargetName
0x14012babc  and     rcx, rax
0x14012babf  lea     rax, [rsp+140h+var_D8]
0x14012bac4  mov     [rsp+140h+var_E8], rax; ptsExpiry
0x14012bac9  lea     rax, [rsp+140h+var_E0]
0x14012bace  mov     [rsp+140h+pfContextAttr], rax; pfContextAttr
0x14012bad3  lea     rax, [rbp+40h+pInput]
0x14012bad7  mov     [rsp+140h+pOutput], rax; pOutput
0x14012badc  lea     rax, [rbp+40h+phNewContext]
0x14012bae0  mov     [rsp+140h+ptsExpiry], rax; phNewContext
0x14012bae5  mov     dword ptr [rsp+140h+phCredential], r12d; Reserved2
0x14012baea  mov     [rsp+140h+pvGetKeyArgument], rcx; pInput
0x14012baef  lea     rcx, [rbp+40h+var_58]; phCredential
0x14012baf3  mov     dword ptr [rsp+140h+pGetKeyFn], 10h; TargetDataRep
0x14012bafb  mov     dword ptr [rsp+140h+pAuthData], r12d; Reserved1
0x14012bb00  call    cs:__imp_InitializeSecurityContextW
0x14012bb07  nop     dword ptr [rax+rax+00h]
0x14012bb0c  test    eax, eax
0x14012bb0e  jz      short loc_14012BB1B
0x14012bb10  cmp     eax, 90312h
0x14012bb15  jnz     loc_14012B979
0x14012bb1b  mov     rcx, [rsp+140h+pvContextBuffer+8]; pvContextBuffer
0x14012bb20  lea     r14, [rbp+40h+phNewContext]
0x14012bb24  test    rcx, rcx
0x14012bb27  jz      short loc_14012BB3F
0x14012bb29  call    cs:__imp_FreeContextBuffer
0x14012bb30  nop     dword ptr [rax+rax+00h]
0x14012bb35  mov     dword ptr [rsp+140h+pvContextBuffer], r12d
0x14012bb3a  mov     [rsp+140h+pvContextBuffer+8], r12
0x14012bb3f  lea     rax, [rsp+140h+var_D8]
0x14012bb44  mov     r9d, 100h; fContextReq
0x14012bb4a  mov     [rsp+140h+ptsExpiry], rax; ptsExpiry
0x14012bb4f  lea     r8, [rbp+40h+pInput]; pInput
0x14012bb53  lea     rax, [rsp+140h+var_E0]
0x14012bb58  mov     rdx, rsi; phContext
0x14012bb5b  mov     [rsp+140h+phCredential], rax; pfContextAttr
0x14012bb60  lea     rcx, [rbp+40h+var_68]; phCredential
0x14012bb64  lea     rax, [rbp+40h+var_A0]
0x14012bb68  mov     [rsp+140h+pvGetKeyArgument], rax; pOutput
0x14012bb6d  lea     rax, [rbp+40h+phContext]
0x14012bb71  mov     [rsp+140h+pGetKeyFn], rax; phNewContext
0x14012bb76  mov     dword ptr [rsp+140h+pAuthData], 10h; TargetDataRep
0x14012bb7e  call    cs:__imp_AcceptSecurityContext
0x14012bb85  nop     dword ptr [rax+rax+00h]
0x14012bb8a  test    eax, eax
0x14012bb8c  jz      short loc_14012BB99
0x14012bb8e  cmp     eax, 90312h
0x14012bb93  jnz     loc_14012B979
0x14012bb99  lea     rsi, [rbp+40h+phContext]
0x14012bb9d  cmp     eax, 90312h
0x14012bba2  jz      loc_14012BA84
0x14012bba8  test    eax, eax
0x14012bbaa  jnz     loc_14012B979
0x14012bbb0  mov     rdx, rbx; Token
0x14012bbb3  lea     rcx, [rbp+40h+phContext]; phContext
0x14012bbb7  call    cs:__imp_QuerySecurityContextToken
0x14012bbbe  nop     dword ptr [rax+rax+00h]
0x14012bbc3  test    eax, eax
0x14012bbc5  jnz     loc_14012B979
0x14012bbcb  mov     rbx, r12
0x14012bbce  jmp     loc_14012B987
```
