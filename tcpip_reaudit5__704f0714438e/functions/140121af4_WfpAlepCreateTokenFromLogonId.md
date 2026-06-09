# WfpAlepCreateTokenFromLogonId

- ea: `0x140121af4`
- end: `0x140121e43`
- name: `WfpAlepCreateTokenFromLogonId`
- size: `847`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140121a0c`
- `0x140177550`

## callees

- `0x1400be690`
- `0x140121af4`
- `0x14014ec1c`
- `0x1401bf4d0`

## import_xrefs

- `ksecdd!FreeContextBuffer` at `0x140121c01`
- `ksecdd!FreeContextBuffer` at `0x140121c16`
- `ksecdd!FreeContextBuffer` at `0x140121cfd`
- `ksecdd!FreeContextBuffer` at `0x140121d99`
- `ksecdd!FreeContextBuffer` at `0x140121c01`
- `ksecdd!FreeContextBuffer` at `0x140121c16`
- `ksecdd!FreeContextBuffer` at `0x140121cfd`
- `ksecdd!FreeContextBuffer` at `0x140121d99`
- `ksecdd!InitializeSecurityContextW` at `0x140121d70`
- `ksecdd!InitializeSecurityContextW` at `0x140121d70`
- `ksecdd!AcceptSecurityContext` at `0x140121dee`
- `ksecdd!AcceptSecurityContext` at `0x140121dee`
- `ksecdd!QuerySecurityContextToken` at `0x140121e27`
- `ksecdd!QuerySecurityContextToken` at `0x140121e27`
- `ksecdd!DeleteSecurityContext` at `0x140121c2a`
- `ksecdd!DeleteSecurityContext` at `0x140121c3e`
- `ksecdd!DeleteSecurityContext` at `0x140121c2a`
- `ksecdd!DeleteSecurityContext` at `0x140121c3e`
- `ksecdd!FreeCredentialsHandle` at `0x140121c53`
- `ksecdd!FreeCredentialsHandle` at `0x140121c68`
- `ksecdd!FreeCredentialsHandle` at `0x140121c53`
- `ksecdd!FreeCredentialsHandle` at `0x140121c68`
- `ksecdd!AcquireCredentialsHandleW` at `0x140121bcb`
- `ksecdd!AcquireCredentialsHandleW` at `0x140121cdd`
- `ksecdd!AcquireCredentialsHandleW` at `0x140121bcb`
- `ksecdd!AcquireCredentialsHandleW` at `0x140121cdd`

## string_xrefs

- `0x140121bd7`: `WfpAlepCreateTokenFromLogonId`

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
0x140121af4  mov     [rsp-8+arg_10], rbx
0x140121af9  push    rbp
0x140121afa  push    rsi
0x140121afb  push    rdi
0x140121afc  push    r12
0x140121afe  push    r13
0x140121b00  push    r14
0x140121b02  push    r15
0x140121b04  lea     rbp, [rsp-10h]
0x140121b09  sub     rsp, 110h
0x140121b10  mov     rax, cs:__security_cookie
0x140121b17  xor     rax, rsp
0x140121b1a  mov     [rbp+40h+var_38], rax
0x140121b1e  xor     r12d, r12d
0x140121b21  mov     [rbp+40h+pvLogonId], rcx
0x140121b25  xorps   xmm0, xmm0
0x140121b28  mov     qword ptr [rbp+40h+pPackage.Length], 0A0008h
0x140121b30  xorps   xmm1, xmm1
0x140121b33  mov     [rsp+140h+var_E0], r12d
0x140121b38  lea     rax, aNtlm; "NTLM"
0x140121b3f  mov     qword ptr [rsp+140h+var_D8], r12
0x140121b44  mov     [rbp+40h+pPackage.Buffer], rax
0x140121b48  lea     r8d, [r12+2]; fCredentialUse
0x140121b4d  lea     rax, [rbp+40h+var_C0]
0x140121b51  mov     [rbp+40h+pInput.ulVersion], r12d
0x140121b55  mov     [rbp+40h+pInput.pBuffers], rax
0x140121b59  lea     edi, [r12+1]
0x140121b5e  lea     rax, [rsp+140h+pvContextBuffer]
0x140121b63  mov     [rbp+40h+pInput.cBuffers], edi
0x140121b66  mov     [rbp+40h+var_A0.pBuffers], rax
0x140121b6a  lea     r9, [rbp+40h+pvLogonId]; pvLogonId
0x140121b6e  lea     rax, [rsp+140h+var_D8]
0x140121b73  mov     [rbp+40h+var_A0.ulVersion], r12d
0x140121b77  mov     [rsp+140h+ptsExpiry], rax; ptsExpiry
0x140121b7c  mov     rbx, rdx
0x140121b7f  lea     rax, [rbp+40h+var_58]
0x140121b83  mov     [rbp+40h+var_A0.cBuffers], edi
0x140121b86  mov     [rsp+140h+phCredential], rax; phCredential
0x140121b8b  lea     rdx, [rbp+40h+pPackage]; pPackage
0x140121b8f  mov     [rsp+140h+pvGetKeyArgument], r12; pvGetKeyArgument
0x140121b94  xor     ecx, ecx; pPrincipal
0x140121b96  movups  xmmword ptr [rbp+40h+var_C0], xmm0
0x140121b9a  mov     [rsp+140h+pGetKeyFn], r12; pGetKeyFn
0x140121b9f  mov     r15b, r12b
0x140121ba2  movups  xmmword ptr [rsp+140h+pvContextBuffer], xmm1
0x140121ba7  mov     [rsp+140h+pAuthData], r12; pAuthData
0x140121bac  mov     r14d, r12d
0x140121baf  movups  xmmword ptr [rbp+40h+var_58.dwLower], xmm0
0x140121bb3  mov     esi, r12d
0x140121bb6  mov     dword ptr [rbp+40h+var_C0+4], r8d
0x140121bba  movups  xmmword ptr [rbp+40h+var_68.dwLower], xmm1
0x140121bbe  mov     dword ptr [rsp+140h+pvContextBuffer+4], r8d
0x140121bc3  movups  xmmword ptr [rbp+40h+phNewContext.dwLower], xmm0
0x140121bc7  movups  xmmword ptr [rbp+40h+phContext.dwLower], xmm1
0x140121bcb  call    cs:__imp_AcquireCredentialsHandleW
0x140121bd2  nop     dword ptr [rax+rax+00h]
0x140121bd7  lea     r13, aWfpalepcreatet; "WfpAlepCreateTokenFromLogonId"
0x140121bde  test    eax, eax
0x140121be0  jz      loc_140121CAF
0x140121be6  mov     dil, r12b
0x140121be9  mov     r8d, eax
0x140121bec  mov     rdx, r13
0x140121bef  call    WfpReportSysErrorAsWinError
0x140121bf4  mov     rbx, rax
0x140121bf7  mov     rcx, [rsp+140h+pvContextBuffer+8]; pvContextBuffer
0x140121bfc  test    rcx, rcx
0x140121bff  jz      short loc_140121C0D
0x140121c01  call    cs:__imp_FreeContextBuffer
0x140121c08  nop     dword ptr [rax+rax+00h]
0x140121c0d  mov     rcx, [rbp+40h+var_C0+8]; pvContextBuffer
0x140121c11  test    rcx, rcx
0x140121c14  jz      short loc_140121C22
0x140121c16  call    cs:__imp_FreeContextBuffer
0x140121c1d  nop     dword ptr [rax+rax+00h]
0x140121c22  test    rsi, rsi
0x140121c25  jz      short loc_140121C36
0x140121c27  mov     rcx, rsi; phContext
0x140121c2a  call    cs:__imp_DeleteSecurityContext
0x140121c31  nop     dword ptr [rax+rax+00h]
0x140121c36  test    r14, r14
0x140121c39  jz      short loc_140121C4A
0x140121c3b  mov     rcx, r14; phContext
0x140121c3e  call    cs:__imp_DeleteSecurityContext
0x140121c45  nop     dword ptr [rax+rax+00h]
0x140121c4a  test    r15b, r15b
0x140121c4d  jz      short loc_140121C5F
0x140121c4f  lea     rcx, [rbp+40h+var_68]; phCredential
0x140121c53  call    cs:__imp_FreeCredentialsHandle
0x140121c5a  nop     dword ptr [rax+rax+00h]
0x140121c5f  test    dil, dil
0x140121c62  jz      short loc_140121C74
0x140121c64  lea     rcx, [rbp+40h+var_58]; phCredential
0x140121c68  call    cs:__imp_FreeCredentialsHandle
0x140121c6f  nop     dword ptr [rax+rax+00h]
0x140121c74  test    rbx, rbx
0x140121c77  jz      short loc_140121C84
0x140121c79  mov     rdx, r13
0x140121c7c  mov     rcx, rbx
0x140121c7f  call    WfpReportError
0x140121c84  mov     rax, rbx
0x140121c87  mov     rcx, [rbp+40h+var_38]
0x140121c8b  xor     rcx, rsp; StackCookie
0x140121c8e  call    __security_check_cookie
0x140121c93  mov     rbx, [rsp+140h+arg_10]
0x140121c9b  add     rsp, 110h
0x140121ca2  pop     r15
0x140121ca4  pop     r14
0x140121ca6  pop     r13
0x140121ca8  pop     r12
0x140121caa  pop     rdi
0x140121cab  pop     rsi
0x140121cac  pop     rbp
0x140121cad  retn
0x140121caf  lea     rax, [rsp+140h+var_D8]
0x140121cb4  xor     r9d, r9d; pvLogonId
0x140121cb7  mov     [rsp+140h+ptsExpiry], rax; ptsExpiry
0x140121cbc  lea     rdx, [rbp+40h+pPackage]; pPackage
0x140121cc0  lea     rax, [rbp+40h+var_68]
0x140121cc4  mov     r8d, edi; fCredentialUse
0x140121cc7  mov     [rsp+140h+phCredential], rax; phCredential
0x140121ccc  xor     ecx, ecx; pPrincipal
0x140121cce  mov     [rsp+140h+pvGetKeyArgument], r12; pvGetKeyArgument
0x140121cd3  mov     [rsp+140h+pGetKeyFn], r12; pGetKeyFn
0x140121cd8  mov     [rsp+140h+pAuthData], r12; pAuthData
0x140121cdd  call    cs:__imp_AcquireCredentialsHandleW
0x140121ce4  nop     dword ptr [rax+rax+00h]
0x140121ce9  test    eax, eax
0x140121ceb  jnz     loc_140121BE9
0x140121cf1  mov     r15b, dil
0x140121cf4  mov     rcx, [rbp+40h+var_C0+8]; pvContextBuffer
0x140121cf8  test    rcx, rcx
0x140121cfb  jz      short loc_140121D11
0x140121cfd  call    cs:__imp_FreeContextBuffer
0x140121d04  nop     dword ptr [rax+rax+00h]
0x140121d09  mov     dword ptr [rbp+40h+var_C0], r12d
0x140121d0d  mov     [rbp+40h+var_C0+8], r12
0x140121d11  mov     rax, [rsp+140h+pvContextBuffer+8]
0x140121d16  mov     r9d, 100h; fContextReq
0x140121d1c  neg     rax
0x140121d1f  mov     rdx, r14; phContext
0x140121d22  lea     rax, [rbp+40h+var_A0]
0x140121d26  sbb     rcx, rcx
0x140121d29  xor     r8d, r8d; pTargetName
0x140121d2c  and     rcx, rax
0x140121d2f  lea     rax, [rsp+140h+var_D8]
0x140121d34  mov     [rsp+140h+var_E8], rax; ptsExpiry
0x140121d39  lea     rax, [rsp+140h+var_E0]
0x140121d3e  mov     [rsp+140h+pfContextAttr], rax; pfContextAttr
0x140121d43  lea     rax, [rbp+40h+pInput]
0x140121d47  mov     [rsp+140h+pOutput], rax; pOutput
0x140121d4c  lea     rax, [rbp+40h+phNewContext]
0x140121d50  mov     [rsp+140h+ptsExpiry], rax; phNewContext
0x140121d55  mov     dword ptr [rsp+140h+phCredential], r12d; Reserved2
0x140121d5a  mov     [rsp+140h+pvGetKeyArgument], rcx; pInput
0x140121d5f  lea     rcx, [rbp+40h+var_58]; phCredential
0x140121d63  mov     dword ptr [rsp+140h+pGetKeyFn], 10h; TargetDataRep
0x140121d6b  mov     dword ptr [rsp+140h+pAuthData], r12d; Reserved1
0x140121d70  call    cs:__imp_InitializeSecurityContextW
0x140121d77  nop     dword ptr [rax+rax+00h]
0x140121d7c  test    eax, eax
0x140121d7e  jz      short loc_140121D8B
0x140121d80  cmp     eax, 90312h
0x140121d85  jnz     loc_140121BE9
0x140121d8b  mov     rcx, [rsp+140h+pvContextBuffer+8]; pvContextBuffer
0x140121d90  lea     r14, [rbp+40h+phNewContext]
0x140121d94  test    rcx, rcx
0x140121d97  jz      short loc_140121DAF
0x140121d99  call    cs:__imp_FreeContextBuffer
0x140121da0  nop     dword ptr [rax+rax+00h]
0x140121da5  mov     dword ptr [rsp+140h+pvContextBuffer], r12d
0x140121daa  mov     [rsp+140h+pvContextBuffer+8], r12
0x140121daf  lea     rax, [rsp+140h+var_D8]
0x140121db4  mov     r9d, 100h; fContextReq
0x140121dba  mov     [rsp+140h+ptsExpiry], rax; ptsExpiry
0x140121dbf  lea     r8, [rbp+40h+pInput]; pInput
0x140121dc3  lea     rax, [rsp+140h+var_E0]
0x140121dc8  mov     rdx, rsi; phContext
0x140121dcb  mov     [rsp+140h+phCredential], rax; pfContextAttr
0x140121dd0  lea     rcx, [rbp+40h+var_68]; phCredential
0x140121dd4  lea     rax, [rbp+40h+var_A0]
0x140121dd8  mov     [rsp+140h+pvGetKeyArgument], rax; pOutput
0x140121ddd  lea     rax, [rbp+40h+phContext]
0x140121de1  mov     [rsp+140h+pGetKeyFn], rax; phNewContext
0x140121de6  mov     dword ptr [rsp+140h+pAuthData], 10h; TargetDataRep
0x140121dee  call    cs:__imp_AcceptSecurityContext
0x140121df5  nop     dword ptr [rax+rax+00h]
0x140121dfa  test    eax, eax
0x140121dfc  jz      short loc_140121E09
0x140121dfe  cmp     eax, 90312h
0x140121e03  jnz     loc_140121BE9
0x140121e09  lea     rsi, [rbp+40h+phContext]
0x140121e0d  cmp     eax, 90312h
0x140121e12  jz      loc_140121CF4
0x140121e18  test    eax, eax
0x140121e1a  jnz     loc_140121BE9
0x140121e20  mov     rdx, rbx; Token
0x140121e23  lea     rcx, [rbp+40h+phContext]; phContext
0x140121e27  call    cs:__imp_QuerySecurityContextToken
0x140121e2e  nop     dword ptr [rax+rax+00h]
0x140121e33  test    eax, eax
0x140121e35  jnz     loc_140121BE9
0x140121e3b  mov     rbx, r12
0x140121e3e  jmp     loc_140121BF7
```
