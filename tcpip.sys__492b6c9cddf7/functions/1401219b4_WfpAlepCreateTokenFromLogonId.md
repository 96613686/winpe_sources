# WfpAlepCreateTokenFromLogonId

- ea: `0x1401219b4`
- end: `0x140121d03`
- name: `WfpAlepCreateTokenFromLogonId`
- size: `847`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1401218cc`
- `0x140177410`

## callees

- `0x1400be890`
- `0x1401219b4`
- `0x14014eadc`
- `0x1401bf390`

## import_xrefs

- `ksecdd!FreeContextBuffer` at `0x140121ac1`
- `ksecdd!FreeContextBuffer` at `0x140121ad6`
- `ksecdd!FreeContextBuffer` at `0x140121bbd`
- `ksecdd!FreeContextBuffer` at `0x140121c59`
- `ksecdd!FreeContextBuffer` at `0x140121ac1`
- `ksecdd!FreeContextBuffer` at `0x140121ad6`
- `ksecdd!FreeContextBuffer` at `0x140121bbd`
- `ksecdd!FreeContextBuffer` at `0x140121c59`
- `ksecdd!InitializeSecurityContextW` at `0x140121c30`
- `ksecdd!InitializeSecurityContextW` at `0x140121c30`
- `ksecdd!AcceptSecurityContext` at `0x140121cae`
- `ksecdd!AcceptSecurityContext` at `0x140121cae`
- `ksecdd!QuerySecurityContextToken` at `0x140121ce7`
- `ksecdd!QuerySecurityContextToken` at `0x140121ce7`
- `ksecdd!DeleteSecurityContext` at `0x140121aea`
- `ksecdd!DeleteSecurityContext` at `0x140121afe`
- `ksecdd!DeleteSecurityContext` at `0x140121aea`
- `ksecdd!DeleteSecurityContext` at `0x140121afe`
- `ksecdd!FreeCredentialsHandle` at `0x140121b13`
- `ksecdd!FreeCredentialsHandle` at `0x140121b28`
- `ksecdd!FreeCredentialsHandle` at `0x140121b13`
- `ksecdd!FreeCredentialsHandle` at `0x140121b28`
- `ksecdd!AcquireCredentialsHandleW` at `0x140121a8b`
- `ksecdd!AcquireCredentialsHandleW` at `0x140121b9d`
- `ksecdd!AcquireCredentialsHandleW` at `0x140121a8b`
- `ksecdd!AcquireCredentialsHandleW` at `0x140121b9d`

## string_xrefs

- `0x140121a97`: `WfpAlepCreateTokenFromLogonId`

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
0x1401219b4  mov     [rsp-8+arg_10], rbx
0x1401219b9  push    rbp
0x1401219ba  push    rsi
0x1401219bb  push    rdi
0x1401219bc  push    r12
0x1401219be  push    r13
0x1401219c0  push    r14
0x1401219c2  push    r15
0x1401219c4  lea     rbp, [rsp-10h]
0x1401219c9  sub     rsp, 110h
0x1401219d0  mov     rax, cs:__security_cookie
0x1401219d7  xor     rax, rsp
0x1401219da  mov     [rbp+40h+var_38], rax
0x1401219de  xor     r12d, r12d
0x1401219e1  mov     [rbp+40h+pvLogonId], rcx
0x1401219e5  xorps   xmm0, xmm0
0x1401219e8  mov     qword ptr [rbp+40h+pPackage.Length], 0A0008h
0x1401219f0  xorps   xmm1, xmm1
0x1401219f3  mov     [rsp+140h+var_E0], r12d
0x1401219f8  lea     rax, aNtlm; "NTLM"
0x1401219ff  mov     qword ptr [rsp+140h+var_D8], r12
0x140121a04  mov     [rbp+40h+pPackage.Buffer], rax
0x140121a08  lea     r8d, [r12+2]; fCredentialUse
0x140121a0d  lea     rax, [rbp+40h+var_C0]
0x140121a11  mov     [rbp+40h+pInput.ulVersion], r12d
0x140121a15  mov     [rbp+40h+pInput.pBuffers], rax
0x140121a19  lea     edi, [r12+1]
0x140121a1e  lea     rax, [rsp+140h+pvContextBuffer]
0x140121a23  mov     [rbp+40h+pInput.cBuffers], edi
0x140121a26  mov     [rbp+40h+var_A0.pBuffers], rax
0x140121a2a  lea     r9, [rbp+40h+pvLogonId]; pvLogonId
0x140121a2e  lea     rax, [rsp+140h+var_D8]
0x140121a33  mov     [rbp+40h+var_A0.ulVersion], r12d
0x140121a37  mov     [rsp+140h+ptsExpiry], rax; ptsExpiry
0x140121a3c  mov     rbx, rdx
0x140121a3f  lea     rax, [rbp+40h+var_58]
0x140121a43  mov     [rbp+40h+var_A0.cBuffers], edi
0x140121a46  mov     [rsp+140h+phCredential], rax; phCredential
0x140121a4b  lea     rdx, [rbp+40h+pPackage]; pPackage
0x140121a4f  mov     [rsp+140h+pvGetKeyArgument], r12; pvGetKeyArgument
0x140121a54  xor     ecx, ecx; pPrincipal
0x140121a56  movups  xmmword ptr [rbp+40h+var_C0], xmm0
0x140121a5a  mov     [rsp+140h+pGetKeyFn], r12; pGetKeyFn
0x140121a5f  mov     r15b, r12b
0x140121a62  movups  xmmword ptr [rsp+140h+pvContextBuffer], xmm1
0x140121a67  mov     [rsp+140h+pAuthData], r12; pAuthData
0x140121a6c  mov     r14d, r12d
0x140121a6f  movups  xmmword ptr [rbp+40h+var_58.dwLower], xmm0
0x140121a73  mov     esi, r12d
0x140121a76  mov     dword ptr [rbp+40h+var_C0+4], r8d
0x140121a7a  movups  xmmword ptr [rbp+40h+var_68.dwLower], xmm1
0x140121a7e  mov     dword ptr [rsp+140h+pvContextBuffer+4], r8d
0x140121a83  movups  xmmword ptr [rbp+40h+phNewContext.dwLower], xmm0
0x140121a87  movups  xmmword ptr [rbp+40h+phContext.dwLower], xmm1
0x140121a8b  call    cs:__imp_AcquireCredentialsHandleW
0x140121a92  nop     dword ptr [rax+rax+00h]
0x140121a97  lea     r13, aWfpalepcreatet; "WfpAlepCreateTokenFromLogonId"
0x140121a9e  test    eax, eax
0x140121aa0  jz      loc_140121B6F
0x140121aa6  mov     dil, r12b
0x140121aa9  mov     r8d, eax
0x140121aac  mov     rdx, r13
0x140121aaf  call    WfpReportSysErrorAsWinError
0x140121ab4  mov     rbx, rax
0x140121ab7  mov     rcx, [rsp+140h+pvContextBuffer+8]; pvContextBuffer
0x140121abc  test    rcx, rcx
0x140121abf  jz      short loc_140121ACD
0x140121ac1  call    cs:__imp_FreeContextBuffer
0x140121ac8  nop     dword ptr [rax+rax+00h]
0x140121acd  mov     rcx, [rbp+40h+var_C0+8]; pvContextBuffer
0x140121ad1  test    rcx, rcx
0x140121ad4  jz      short loc_140121AE2
0x140121ad6  call    cs:__imp_FreeContextBuffer
0x140121add  nop     dword ptr [rax+rax+00h]
0x140121ae2  test    rsi, rsi
0x140121ae5  jz      short loc_140121AF6
0x140121ae7  mov     rcx, rsi; phContext
0x140121aea  call    cs:__imp_DeleteSecurityContext
0x140121af1  nop     dword ptr [rax+rax+00h]
0x140121af6  test    r14, r14
0x140121af9  jz      short loc_140121B0A
0x140121afb  mov     rcx, r14; phContext
0x140121afe  call    cs:__imp_DeleteSecurityContext
0x140121b05  nop     dword ptr [rax+rax+00h]
0x140121b0a  test    r15b, r15b
0x140121b0d  jz      short loc_140121B1F
0x140121b0f  lea     rcx, [rbp+40h+var_68]; phCredential
0x140121b13  call    cs:__imp_FreeCredentialsHandle
0x140121b1a  nop     dword ptr [rax+rax+00h]
0x140121b1f  test    dil, dil
0x140121b22  jz      short loc_140121B34
0x140121b24  lea     rcx, [rbp+40h+var_58]; phCredential
0x140121b28  call    cs:__imp_FreeCredentialsHandle
0x140121b2f  nop     dword ptr [rax+rax+00h]
0x140121b34  test    rbx, rbx
0x140121b37  jz      short loc_140121B44
0x140121b39  mov     rdx, r13
0x140121b3c  mov     rcx, rbx
0x140121b3f  call    WfpReportError
0x140121b44  mov     rax, rbx
0x140121b47  mov     rcx, [rbp+40h+var_38]
0x140121b4b  xor     rcx, rsp; StackCookie
0x140121b4e  call    __security_check_cookie
0x140121b53  mov     rbx, [rsp+140h+arg_10]
0x140121b5b  add     rsp, 110h
0x140121b62  pop     r15
0x140121b64  pop     r14
0x140121b66  pop     r13
0x140121b68  pop     r12
0x140121b6a  pop     rdi
0x140121b6b  pop     rsi
0x140121b6c  pop     rbp
0x140121b6d  retn
0x140121b6f  lea     rax, [rsp+140h+var_D8]
0x140121b74  xor     r9d, r9d; pvLogonId
0x140121b77  mov     [rsp+140h+ptsExpiry], rax; ptsExpiry
0x140121b7c  lea     rdx, [rbp+40h+pPackage]; pPackage
0x140121b80  lea     rax, [rbp+40h+var_68]
0x140121b84  mov     r8d, edi; fCredentialUse
0x140121b87  mov     [rsp+140h+phCredential], rax; phCredential
0x140121b8c  xor     ecx, ecx; pPrincipal
0x140121b8e  mov     [rsp+140h+pvGetKeyArgument], r12; pvGetKeyArgument
0x140121b93  mov     [rsp+140h+pGetKeyFn], r12; pGetKeyFn
0x140121b98  mov     [rsp+140h+pAuthData], r12; pAuthData
0x140121b9d  call    cs:__imp_AcquireCredentialsHandleW
0x140121ba4  nop     dword ptr [rax+rax+00h]
0x140121ba9  test    eax, eax
0x140121bab  jnz     loc_140121AA9
0x140121bb1  mov     r15b, dil
0x140121bb4  mov     rcx, [rbp+40h+var_C0+8]; pvContextBuffer
0x140121bb8  test    rcx, rcx
0x140121bbb  jz      short loc_140121BD1
0x140121bbd  call    cs:__imp_FreeContextBuffer
0x140121bc4  nop     dword ptr [rax+rax+00h]
0x140121bc9  mov     dword ptr [rbp+40h+var_C0], r12d
0x140121bcd  mov     [rbp+40h+var_C0+8], r12
0x140121bd1  mov     rax, [rsp+140h+pvContextBuffer+8]
0x140121bd6  mov     r9d, 100h; fContextReq
0x140121bdc  neg     rax
0x140121bdf  mov     rdx, r14; phContext
0x140121be2  lea     rax, [rbp+40h+var_A0]
0x140121be6  sbb     rcx, rcx
0x140121be9  xor     r8d, r8d; pTargetName
0x140121bec  and     rcx, rax
0x140121bef  lea     rax, [rsp+140h+var_D8]
0x140121bf4  mov     [rsp+140h+var_E8], rax; ptsExpiry
0x140121bf9  lea     rax, [rsp+140h+var_E0]
0x140121bfe  mov     [rsp+140h+pfContextAttr], rax; pfContextAttr
0x140121c03  lea     rax, [rbp+40h+pInput]
0x140121c07  mov     [rsp+140h+pOutput], rax; pOutput
0x140121c0c  lea     rax, [rbp+40h+phNewContext]
0x140121c10  mov     [rsp+140h+ptsExpiry], rax; phNewContext
0x140121c15  mov     dword ptr [rsp+140h+phCredential], r12d; Reserved2
0x140121c1a  mov     [rsp+140h+pvGetKeyArgument], rcx; pInput
0x140121c1f  lea     rcx, [rbp+40h+var_58]; phCredential
0x140121c23  mov     dword ptr [rsp+140h+pGetKeyFn], 10h; TargetDataRep
0x140121c2b  mov     dword ptr [rsp+140h+pAuthData], r12d; Reserved1
0x140121c30  call    cs:__imp_InitializeSecurityContextW
0x140121c37  nop     dword ptr [rax+rax+00h]
0x140121c3c  test    eax, eax
0x140121c3e  jz      short loc_140121C4B
0x140121c40  cmp     eax, 90312h
0x140121c45  jnz     loc_140121AA9
0x140121c4b  mov     rcx, [rsp+140h+pvContextBuffer+8]; pvContextBuffer
0x140121c50  lea     r14, [rbp+40h+phNewContext]
0x140121c54  test    rcx, rcx
0x140121c57  jz      short loc_140121C6F
0x140121c59  call    cs:__imp_FreeContextBuffer
0x140121c60  nop     dword ptr [rax+rax+00h]
0x140121c65  mov     dword ptr [rsp+140h+pvContextBuffer], r12d
0x140121c6a  mov     [rsp+140h+pvContextBuffer+8], r12
0x140121c6f  lea     rax, [rsp+140h+var_D8]
0x140121c74  mov     r9d, 100h; fContextReq
0x140121c7a  mov     [rsp+140h+ptsExpiry], rax; ptsExpiry
0x140121c7f  lea     r8, [rbp+40h+pInput]; pInput
0x140121c83  lea     rax, [rsp+140h+var_E0]
0x140121c88  mov     rdx, rsi; phContext
0x140121c8b  mov     [rsp+140h+phCredential], rax; pfContextAttr
0x140121c90  lea     rcx, [rbp+40h+var_68]; phCredential
0x140121c94  lea     rax, [rbp+40h+var_A0]
0x140121c98  mov     [rsp+140h+pvGetKeyArgument], rax; pOutput
0x140121c9d  lea     rax, [rbp+40h+phContext]
0x140121ca1  mov     [rsp+140h+pGetKeyFn], rax; phNewContext
0x140121ca6  mov     dword ptr [rsp+140h+pAuthData], 10h; TargetDataRep
0x140121cae  call    cs:__imp_AcceptSecurityContext
0x140121cb5  nop     dword ptr [rax+rax+00h]
0x140121cba  test    eax, eax
0x140121cbc  jz      short loc_140121CC9
0x140121cbe  cmp     eax, 90312h
0x140121cc3  jnz     loc_140121AA9
0x140121cc9  lea     rsi, [rbp+40h+phContext]
0x140121ccd  cmp     eax, 90312h
0x140121cd2  jz      loc_140121BB4
0x140121cd8  test    eax, eax
0x140121cda  jnz     loc_140121AA9
0x140121ce0  mov     rdx, rbx; Token
0x140121ce3  lea     rcx, [rbp+40h+phContext]; phContext
0x140121ce7  call    cs:__imp_QuerySecurityContextToken
0x140121cee  nop     dword ptr [rax+rax+00h]
0x140121cf3  test    eax, eax
0x140121cf5  jnz     loc_140121AA9
0x140121cfb  mov     rbx, r12
0x140121cfe  jmp     loc_140121AB7
```
