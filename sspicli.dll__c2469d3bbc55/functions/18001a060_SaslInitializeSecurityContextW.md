# SaslInitializeSecurityContextW

- ea: `0x18001a060`
- end: `0x18001a1ff`
- name: `SaslInitializeSecurityContextW`
- size: `415`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, LPWSTR pszTargetName, unsigned int fContextReq, unsigned int Reserved1, unsigned int TargetDataRep, PSecBufferDesc pInput, unsigned int Reserved2, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
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
- `0x18001a060`

## pseudocode

```c
SECURITY_STATUS __stdcall SaslInitializeSecurityContextW(
        PCredHandle phCredential,
        PCtxtHandle phContext,
        LPWSTR pszTargetName,
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
  struct _SASL_CONTEXT *v13; // rbx
  struct _SecBufferDesc *v14; // r14
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
  v13 = 0;
  v14 = pInput;
  v27.QuadPart = 0;
  if ( !phContext || !phContext->dwLower )
    goto LABEL_9;
  Context = SaslFindContext(phContext, 0);
  v13 = Context;
  if ( !Context )
    return -2146893055;
  if ( *((_DWORD *)Context + 10) == 1 && (result = SaslCrackServerCookie(v14, v12, Context), result >= 0) )
  {
    *pfContextAttr = *((_DWORD *)v13 + 13);
    if ( ptsExpiry )
      *ptsExpiry = *(SECURITY_INTEGER *)((char *)v13 + 32);
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
            v14,
            Reserved2,
            phNewContext,
            v26,
            pfContextAttr,
            &v27,
            1u);
    if ( v23 < 0 )
    {
      if ( v13 )
        SaslDeleteContext(v13);
    }
    else
    {
      if ( v13 )
      {
        *((struct _SecHandle *)v13 + 1) = *v22;
      }
      else
      {
        v24 = SaslCreateContext(v22);
        v13 = v24;
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
        *((_DWORD *)v13 + 10) = 1;
        *((_DWORD *)v13 + 13) = *v21;
        *((union _LARGE_INTEGER *)v13 + 4) = v27;
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
0x18001a060  mov     rax, rsp
0x18001a063  push    rbx
0x18001a064  push    rbp
0x18001a065  push    rsi
0x18001a066  push    rdi
0x18001a067  push    r12
0x18001a069  push    r13
0x18001a06b  push    r14
0x18001a06d  push    r15
0x18001a06f  sub     rsp, 78h
0x18001a073  mov     rsi, [rsp+0B8h+pOutput]
0x18001a07b  xor     ebx, ebx
0x18001a07d  mov     r14, [rsp+0B8h+pInput]
0x18001a085  mov     ebp, r9d
0x18001a088  mov     [rax+10h], rbx
0x18001a08c  mov     r12, r8
0x18001a08f  mov     rdi, rdx
0x18001a092  mov     r13, rcx
0x18001a095  test    rdx, rdx
0x18001a098  jz      short loc_18001A0FD
0x18001a09a  cmp     [rdx], rbx
0x18001a09d  jz      short loc_18001A0FD
0x18001a09f  xor     edx, edx; int
0x18001a0a1  mov     rcx, rdi; struct _SecHandle *
0x18001a0a4  call    ?SaslFindContext@@YAPEAU_SASL_CONTEXT@@PEAU_SecHandle@@H@Z; SaslFindContext(_SecHandle *,int)
0x18001a0a9  mov     rbx, rax
0x18001a0ac  test    rax, rax
0x18001a0af  jnz     short loc_18001A0BB
0x18001a0b1  mov     eax, 80090301h
0x18001a0b6  jmp     loc_18001A1EE
0x18001a0bb  cmp     dword ptr [rax+28h], 1
0x18001a0bf  jnz     short loc_18001A0FD
0x18001a0c1  mov     r8, rbx; struct _SASL_CONTEXT *
0x18001a0c4  mov     rdx, rsi; struct _SecBufferDesc *
0x18001a0c7  mov     rcx, r14; struct _SecBufferDesc *
0x18001a0ca  call    ?SaslCrackServerCookie@@YAJPEAU_SecBufferDesc@@0PEAU_SASL_CONTEXT@@@Z; SaslCrackServerCookie(_SecBufferDesc *,_SecBufferDesc *,_SASL_CONTEXT *)
0x18001a0cf  test    eax, eax
0x18001a0d1  js      short loc_18001A0FD
0x18001a0d3  mov     edx, [rbx+34h]
0x18001a0d6  mov     rcx, [rsp+0B8h+pfContextAttr]
0x18001a0de  mov     [rcx], edx
0x18001a0e0  mov     rdx, [rsp+0B8h+ptsExpiry]
0x18001a0e8  test    rdx, rdx
0x18001a0eb  jz      loc_18001A1EE
0x18001a0f1  mov     rcx, [rbx+20h]
0x18001a0f5  mov     [rdx], rcx
0x18001a0f8  jmp     loc_18001A1EE
0x18001a0fd  mov     r15, [rsp+0B8h+pfContextAttr]
0x18001a105  lea     rax, [rsp+0B8h+arg_8]
0x18001a10d  mov     [rsp+0B8h+var_58], 1; unsigned __int8
0x18001a112  mov     r9d, ebp
0x18001a115  mov     [rsp+0B8h+var_60], rax; union _LARGE_INTEGER *
0x18001a11a  or      r9d, 10010h; unsigned int
0x18001a121  mov     eax, [rsp+0B8h+Reserved2]
0x18001a128  mov     r8, r12; void *
0x18001a12b  mov     [rsp+0B8h+var_68], r15; unsigned int *
0x18001a130  mov     rdx, rdi; struct _SecHandle *
0x18001a133  mov     [rsp+0B8h+var_70], rsi; struct _SecBufferDesc *
0x18001a138  mov     rcx, r13; struct _SecHandle *
0x18001a13b  mov     rsi, [rsp+0B8h+phNewContext]
0x18001a143  mov     [rsp+0B8h+var_78], rsi; struct _SecHandle *
0x18001a148  mov     [rsp+0B8h+var_80], eax; unsigned int
0x18001a14c  mov     eax, [rsp+0B8h+TargetDataRep]
0x18001a153  mov     [rsp+0B8h+var_88], r14; struct _SecBufferDesc *
0x18001a158  mov     [rsp+0B8h+var_90], eax; unsigned int
0x18001a15c  mov     eax, [rsp+0B8h+Reserved1]
0x18001a163  mov     [rsp+0B8h+var_98], eax; unsigned int
0x18001a167  call    ?InitializeSecurityContextCommon@@YAJPEAU_SecHandle@@0PEAXKKKPEAU_SecBufferDesc@@K02PEAKPEAT_LARGE_INTEGER@@E@Z; InitializeSecurityContextCommon(_SecHandle *,_SecHandle *,void *,ulong,ulong,ulong,_SecBufferDesc *,ulong,_SecHandle *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar)
0x18001a16c  mov     edi, eax
0x18001a16e  test    eax, eax
0x18001a170  js      short loc_18001A1DF
0x18001a172  test    rbx, rbx
0x18001a175  jnz     short loc_18001A19B
0x18001a177  mov     rcx, rsi; struct _SecHandle *
0x18001a17a  call    ?SaslCreateContext@@YAPEAU_SASL_CONTEXT@@PEAU_SecHandle@@@Z; SaslCreateContext(_SecHandle *)
0x18001a17f  mov     rbx, rax
0x18001a182  test    rax, rax
0x18001a185  jz      short loc_18001A18C
0x18001a187  mov     [rax+30h], ebp
0x18001a18a  jmp     short loc_18001A1A3
0x18001a18c  mov     rcx, rsi; phContext
0x18001a18f  mov     edi, 80090300h
0x18001a194  call    DeleteSecurityContext
0x18001a199  jmp     short loc_18001A1A3
0x18001a19b  movups  xmm0, xmmword ptr [rsi]
0x18001a19e  movdqu  xmmword ptr [rbx+10h], xmm0
0x18001a1a3  test    edi, edi
0x18001a1a5  jnz     short loc_18001A1EC
0x18001a1a7  mov     rcx, [rsp+0B8h+ptsExpiry]
0x18001a1af  mov     dword ptr [rbx+28h], 1
0x18001a1b6  mov     eax, [r15]
0x18001a1b9  mov     [rbx+34h], eax
0x18001a1bc  mov     rax, qword ptr [rsp+0B8h+arg_8]
0x18001a1c4  mov     [rbx+20h], rax
0x18001a1c8  test    rcx, rcx
0x18001a1cb  jz      short loc_18001A1D8
0x18001a1cd  mov     rax, qword ptr [rsp+0B8h+arg_8]
0x18001a1d5  mov     [rcx], rax
0x18001a1d8  mov     edi, 90312h
0x18001a1dd  jmp     short loc_18001A1EC
0x18001a1df  test    rbx, rbx
0x18001a1e2  jz      short loc_18001A1EC
0x18001a1e4  mov     rcx, rbx; struct _SASL_CONTEXT *
0x18001a1e7  call    ?SaslDeleteContext@@YAXPEAU_SASL_CONTEXT@@@Z; SaslDeleteContext(_SASL_CONTEXT *)
0x18001a1ec  mov     eax, edi
0x18001a1ee  add     rsp, 78h
0x18001a1f2  pop     r15
0x18001a1f4  pop     r14
0x18001a1f6  pop     r13
0x18001a1f8  pop     r12
0x18001a1fa  pop     rdi
0x18001a1fb  pop     rsi
0x18001a1fc  pop     rbp
0x18001a1fd  pop     rbx
0x18001a1fe  retn
```
