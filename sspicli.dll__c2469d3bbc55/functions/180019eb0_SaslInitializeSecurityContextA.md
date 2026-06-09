# SaslInitializeSecurityContextA

- ea: `0x180019eb0`
- end: `0x18001a053`
- name: `SaslInitializeSecurityContextA`
- size: `419`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, LPSTR pszTargetName, unsigned int fContextReq, unsigned int Reserved1, unsigned int TargetDataRep, PSecBufferDesc pInput, unsigned int Reserved2, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001b70`
- `0x180003670`
- `0x1800136dc`
- `0x180019470`
- `0x18001951c`
- `0x1800195c4`
- `0x180019eb0`

## pseudocode

```c
SECURITY_STATUS __stdcall SaslInitializeSecurityContextA(
        PCredHandle phCredential,
        PCtxtHandle phContext,
        LPSTR pszTargetName,
        unsigned int fContextReq,
        unsigned int Reserved1,
        unsigned int TargetDataRep,
        PSecBufferDesc pInput,
        unsigned int Reserved2,
        PCtxtHandle phNewContext,
        PSecBufferDesc pOutput,
        unsigned int *pfContextAttr,
        PTimeStamp ptsExpiry)
{
  struct _SecBufferDesc *v12; // rsi
  struct _SecBufferDesc *v13; // r14
  struct _SASL_CONTEXT *v18; // rbx
  struct _SASL_CONTEXT *Context; // rax
  SECURITY_STATUS result; // eax
  unsigned int *v21; // r15
  PCtxtHandle v22; // rsi
  SECURITY_STATUS v23; // edi
  struct _SASL_CONTEXT *v24; // rax
  PTimeStamp v25; // rcx
  struct _SecBufferDesc *v26; // [rsp+48h] [rbp-70h]
  union _LARGE_INTEGER v27; // [rsp+C8h] [rbp+10h] BYREF

  v12 = pOutput;
  v13 = pInput;
  v27.QuadPart = 0;
  v18 = 0;
  if ( !phContext || !phContext->dwLower )
    goto LABEL_9;
  Context = SaslFindContext(phContext, 0);
  v18 = Context;
  if ( !Context )
    return -2146893055;
  if ( *((_DWORD *)Context + 10) == 1 && (result = SaslCrackServerCookie(v13, v12, Context), result >= 0) )
  {
    *pfContextAttr = *((_DWORD *)v18 + 13);
    if ( ptsExpiry )
      *ptsExpiry = *(SECURITY_INTEGER *)((char *)v18 + 32);
  }
  else
  {
LABEL_9:
    v21 = pfContextAttr;
    v26 = v12;
    v22 = phNewContext;
    v23 = InitializeSecurityContextCommon(
            phCredential,
            phContext,
            pszTargetName,
            fContextReq | 0x10010,
            Reserved1,
            TargetDataRep,
            v13,
            Reserved2,
            phNewContext,
            v26,
            pfContextAttr,
            &v27,
            0);
    if ( v23 < 0 )
    {
      if ( v18 )
        SaslDeleteContext(v18);
    }
    else
    {
      if ( v18 )
      {
        *((struct _SecHandle *)v18 + 1) = *v22;
      }
      else
      {
        v24 = SaslCreateContext(v22);
        v18 = v24;
        if ( v24 )
        {
          *((_DWORD *)v24 + 12) = fContextReq;
        }
        else
        {
          v23 = -2146893056;
          DeleteSecurityContext(v22);
        }
      }
      if ( !v23 )
      {
        v25 = ptsExpiry;
        *((_DWORD *)v18 + 10) = 1;
        *((_DWORD *)v18 + 13) = *v21;
        *((union _LARGE_INTEGER *)v18 + 4) = v27;
        if ( v25 )
          *v25 = v27;
        return 590610;
      }
    }
    return v23;
  }
  return result;
}

```

## disassembly

```asm
0x180019eb0  mov     rax, rsp
0x180019eb3  push    rbx
0x180019eb4  push    rbp
0x180019eb5  push    rsi
0x180019eb6  push    rdi
0x180019eb7  push    r12
0x180019eb9  push    r13
0x180019ebb  push    r14
0x180019ebd  push    r15
0x180019ebf  sub     rsp, 78h
0x180019ec3  mov     rsi, [rsp+0B8h+pOutput]
0x180019ecb  xor     r15d, r15d
0x180019ece  mov     r14, [rsp+0B8h+pInput]
0x180019ed6  mov     ebp, r9d
0x180019ed9  mov     [rax+10h], r15
0x180019edd  mov     r12, r8
0x180019ee0  mov     rdi, rdx
0x180019ee3  mov     r13, rcx
0x180019ee6  mov     ebx, r15d
0x180019ee9  test    rdx, rdx
0x180019eec  jz      short loc_180019F51
0x180019eee  cmp     [rdx], r15
0x180019ef1  jz      short loc_180019F51
0x180019ef3  xor     edx, edx; int
0x180019ef5  mov     rcx, rdi; struct _SecHandle *
0x180019ef8  call    ?SaslFindContext@@YAPEAU_SASL_CONTEXT@@PEAU_SecHandle@@H@Z; SaslFindContext(_SecHandle *,int)
0x180019efd  mov     rbx, rax
0x180019f00  test    rax, rax
0x180019f03  jnz     short loc_180019F0F
0x180019f05  mov     eax, 80090301h
0x180019f0a  jmp     loc_18001A042
0x180019f0f  cmp     dword ptr [rax+28h], 1
0x180019f13  jnz     short loc_180019F51
0x180019f15  mov     r8, rbx; struct _SASL_CONTEXT *
0x180019f18  mov     rdx, rsi; struct _SecBufferDesc *
0x180019f1b  mov     rcx, r14; struct _SecBufferDesc *
0x180019f1e  call    ?SaslCrackServerCookie@@YAJPEAU_SecBufferDesc@@0PEAU_SASL_CONTEXT@@@Z; SaslCrackServerCookie(_SecBufferDesc *,_SecBufferDesc *,_SASL_CONTEXT *)
0x180019f23  test    eax, eax
0x180019f25  js      short loc_180019F51
0x180019f27  mov     edx, [rbx+34h]
0x180019f2a  mov     rcx, [rsp+0B8h+pfContextAttr]
0x180019f32  mov     [rcx], edx
0x180019f34  mov     rdx, [rsp+0B8h+ptsExpiry]
0x180019f3c  test    rdx, rdx
0x180019f3f  jz      loc_18001A042
0x180019f45  mov     rcx, [rbx+20h]
0x180019f49  mov     [rdx], rcx
0x180019f4c  jmp     loc_18001A042
0x180019f51  mov     [rsp+0B8h+var_58], r15b; unsigned __int8
0x180019f56  lea     rax, [rsp+0B8h+arg_8]
0x180019f5e  mov     r15, [rsp+0B8h+pfContextAttr]
0x180019f66  mov     r9d, ebp
0x180019f69  mov     [rsp+0B8h+var_60], rax; union _LARGE_INTEGER *
0x180019f6e  or      r9d, 10010h; unsigned int
0x180019f75  mov     eax, [rsp+0B8h+Reserved2]
0x180019f7c  mov     r8, r12; void *
0x180019f7f  mov     [rsp+0B8h+var_68], r15; unsigned int *
0x180019f84  mov     rdx, rdi; struct _SecHandle *
0x180019f87  mov     [rsp+0B8h+var_70], rsi; struct _SecBufferDesc *
0x180019f8c  mov     rcx, r13; struct _SecHandle *
0x180019f8f  mov     rsi, [rsp+0B8h+phNewContext]
0x180019f97  mov     [rsp+0B8h+var_78], rsi; struct _SecHandle *
0x180019f9c  mov     [rsp+0B8h+var_80], eax; unsigned int
0x180019fa0  mov     eax, [rsp+0B8h+TargetDataRep]
0x180019fa7  mov     [rsp+0B8h+var_88], r14; struct _SecBufferDesc *
0x180019fac  mov     [rsp+0B8h+var_90], eax; unsigned int
0x180019fb0  mov     eax, [rsp+0B8h+Reserved1]
0x180019fb7  mov     [rsp+0B8h+var_98], eax; unsigned int
0x180019fbb  call    ?InitializeSecurityContextCommon@@YAJPEAU_SecHandle@@0PEAXKKKPEAU_SecBufferDesc@@K02PEAKPEAT_LARGE_INTEGER@@E@Z; InitializeSecurityContextCommon(_SecHandle *,_SecHandle *,void *,ulong,ulong,ulong,_SecBufferDesc *,ulong,_SecHandle *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar)
0x180019fc0  mov     edi, eax
0x180019fc2  test    eax, eax
0x180019fc4  js      short loc_18001A033
0x180019fc6  test    rbx, rbx
0x180019fc9  jnz     short loc_180019FEF
0x180019fcb  mov     rcx, rsi; struct _SecHandle *
0x180019fce  call    ?SaslCreateContext@@YAPEAU_SASL_CONTEXT@@PEAU_SecHandle@@@Z; SaslCreateContext(_SecHandle *)
0x180019fd3  mov     rbx, rax
0x180019fd6  test    rax, rax
0x180019fd9  jz      short loc_180019FE0
0x180019fdb  mov     [rax+30h], ebp
0x180019fde  jmp     short loc_180019FF7
0x180019fe0  mov     rcx, rsi; phContext
0x180019fe3  mov     edi, 80090300h
0x180019fe8  call    DeleteSecurityContext
0x180019fed  jmp     short loc_180019FF7
0x180019fef  movups  xmm0, xmmword ptr [rsi]
0x180019ff2  movdqu  xmmword ptr [rbx+10h], xmm0
0x180019ff7  test    edi, edi
0x180019ff9  jnz     short loc_18001A040
0x180019ffb  mov     rcx, [rsp+0B8h+ptsExpiry]
0x18001a003  mov     dword ptr [rbx+28h], 1
0x18001a00a  mov     eax, [r15]
0x18001a00d  mov     [rbx+34h], eax
0x18001a010  mov     rax, qword ptr [rsp+0B8h+arg_8]
0x18001a018  mov     [rbx+20h], rax
0x18001a01c  test    rcx, rcx
0x18001a01f  jz      short loc_18001A02C
0x18001a021  mov     rax, qword ptr [rsp+0B8h+arg_8]
0x18001a029  mov     [rcx], rax
0x18001a02c  mov     edi, 90312h
0x18001a031  jmp     short loc_18001A040
0x18001a033  test    rbx, rbx
0x18001a036  jz      short loc_18001A040
0x18001a038  mov     rcx, rbx; struct _SASL_CONTEXT *
0x18001a03b  call    ?SaslDeleteContext@@YAXPEAU_SASL_CONTEXT@@@Z; SaslDeleteContext(_SASL_CONTEXT *)
0x18001a040  mov     eax, edi
0x18001a042  add     rsp, 78h
0x18001a046  pop     r15
0x18001a048  pop     r14
0x18001a04a  pop     r13
0x18001a04c  pop     r12
0x18001a04e  pop     rdi
0x18001a04f  pop     rsi
0x18001a050  pop     rbp
0x18001a051  pop     rbx
0x18001a052  retn
```
