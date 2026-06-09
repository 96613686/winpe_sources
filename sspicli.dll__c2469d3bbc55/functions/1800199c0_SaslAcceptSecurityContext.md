# SaslAcceptSecurityContext

- ea: `0x1800199c0`
- end: `0x180019bf2`
- name: `SaslAcceptSecurityContext`
- size: `562`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, PSecBufferDesc pInput, unsigned int fContextReq, unsigned int TargetDataRep, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001b70`
- `0x1800104e0`
- `0x1800136dc`
- `0x180019334`
- `0x180019368`
- `0x18001951c`
- `0x1800195c4`
- `0x18001998c`
- `0x1800199c0`

## pseudocode

```c
SECURITY_STATUS __stdcall SaslAcceptSecurityContext(
        PCredHandle phCredential,
        PCtxtHandle phContext,
        PSecBufferDesc pInput,
        unsigned int fContextReq,
        unsigned int TargetDataRep,
        PCtxtHandle phNewContext,
        PSecBufferDesc pOutput,
        unsigned int *pfContextAttr,
        PTimeStamp ptsExpiry)
{
  struct _SASL_CONTEXT *v13; // rbx
  struct _SASL_CONTEXT *Context; // rax
  SECURITY_STATUS result; // eax
  int v16; // ecx
  int v17; // edx
  unsigned int *v18; // r12
  struct _SecBufferDesc *v19; // rbp
  PCtxtHandle v20; // rsi
  unsigned int v21; // edx
  int v22; // edi
  struct _SASL_CONTEXT *v23; // rax
  PTimeStamp v24; // rcx
  struct _SecBufferDesc *v25; // rcx
  SECURITY_INTEGER v26; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int8 v27; // [rsp+B8h] [rbp+10h] BYREF

  v26.QuadPart = 0;
  v13 = 0;
  if ( !phContext || !phContext->dwLower )
    goto LABEL_20;
  Context = SaslFindContext(phContext, 0);
  v13 = Context;
  if ( !Context )
    return -2146893055;
  if ( *((_DWORD *)Context + 10) == 1 )
  {
    result = SaslBuildServerCookie(pOutput, Context);
    if ( result >= 0 )
    {
      *((_DWORD *)v13 + 10) = 2;
      return 590610;
    }
    return result;
  }
  if ( *((_DWORD *)Context + 10) == 2 )
  {
    v27 = 0;
    result = SaslCrackCookie(pInput, Context, &v27);
    if ( result >= 0 )
    {
      v16 = 0;
      if ( (v27 & 2) != 0 && (*((_DWORD *)v13 + 13) & 0x2000C) != 0 && (*((_DWORD *)v13 + 12) & 0x2000C) != 0 )
        v16 = *((_DWORD *)v13 + 13) & 0x2000C;
      v17 = *((_DWORD *)v13 + 13);
      if ( ((v27 >> 2) & ((v17 & 0x10) != 0)) != 0 && (*((_BYTE *)v13 + 48) & 0x10) != 0 )
        v16 |= 0x10u;
      result = 0;
      *((_DWORD *)v13 + 13) = v16 | v17 & 0xFFFDFFE3;
    }
    *pfContextAttr = *((_DWORD *)v13 + 13);
    if ( ptsExpiry )
      *ptsExpiry = *(SECURITY_INTEGER *)((char *)v13 + 32);
  }
  else
  {
LABEL_20:
    v18 = pfContextAttr;
    v19 = pOutput;
    v20 = phNewContext;
    v22 = AcceptSecurityContext(
            phCredential,
            phContext,
            pInput,
            fContextReq | 0x20010,
            TargetDataRep,
            phNewContext,
            pOutput,
            pfContextAttr,
            &v26);
    if ( v22 < 0 )
    {
      if ( v13 )
        SaslDeleteContext(v13);
    }
    else
    {
      if ( v13 )
      {
        *((struct _SecHandle *)v13 + 1) = *v20;
      }
      else
      {
        v23 = SaslCreateContext(v20);
        v13 = v23;
        if ( v23 )
        {
          *((_DWORD *)v23 + 12) = fContextReq;
        }
        else
        {
          DeleteSecurityContext(v20);
          v22 = -2146893056;
        }
      }
      if ( !v22 )
      {
        v24 = ptsExpiry;
        *((_DWORD *)v13 + 13) = *v18;
        *((SECURITY_INTEGER *)v13 + 4) = v26;
        if ( v24 )
          *v24 = v26;
        if ( SaslLocateBuffer(v19, v21) )
        {
          v22 = 590610;
          *((_DWORD *)v13 + 10) = 1;
        }
        else
        {
          *((_DWORD *)v13 + 10) = 2;
          v22 = SaslBuildServerCookie(v25, v13);
          if ( v22 >= 0 )
            return 590610;
        }
      }
    }
    return v22;
  }
  return result;
}

```

## disassembly

```asm
0x1800199c0  push    rbx
0x1800199c2  push    rbp
0x1800199c3  push    rsi
0x1800199c4  push    rdi
0x1800199c5  push    r12
0x1800199c7  push    r13
0x1800199c9  push    r14
0x1800199cb  push    r15
0x1800199cd  sub     rsp, 68h
0x1800199d1  xor     esi, esi
0x1800199d3  mov     r15d, r9d
0x1800199d6  mov     qword ptr [rsp+0A8h+var_58], rsi
0x1800199db  mov     r14, r8
0x1800199de  mov     rdi, rdx
0x1800199e1  mov     r13, rcx
0x1800199e4  mov     ebx, esi
0x1800199e6  test    rdx, rdx
0x1800199e9  jz      loc_180019AE2
0x1800199ef  cmp     [rdx], rsi
0x1800199f2  jz      loc_180019AE2
0x1800199f8  xor     edx, edx; int
0x1800199fa  mov     rcx, rdi; struct _SecHandle *
0x1800199fd  call    ?SaslFindContext@@YAPEAU_SASL_CONTEXT@@PEAU_SecHandle@@H@Z; SaslFindContext(_SecHandle *,int)
0x180019a02  mov     rbx, rax
0x180019a05  test    rax, rax
0x180019a08  jnz     short loc_180019A14
0x180019a0a  mov     eax, 80090301h
0x180019a0f  jmp     loc_180019BE1
0x180019a14  cmp     dword ptr [rax+28h], 1
0x180019a18  jnz     short loc_180019A43
0x180019a1a  mov     rcx, [rsp+0A8h+pOutput]; struct _SecBufferDesc *
0x180019a22  mov     rdx, rbx; struct _SASL_CONTEXT *
0x180019a25  call    ?SaslBuildServerCookie@@YAJPEAU_SecBufferDesc@@PEAU_SASL_CONTEXT@@@Z; SaslBuildServerCookie(_SecBufferDesc *,_SASL_CONTEXT *)
0x180019a2a  test    eax, eax
0x180019a2c  js      loc_180019BE1
0x180019a32  mov     dword ptr [rbx+28h], 2
0x180019a39  mov     eax, 90312h
0x180019a3e  jmp     loc_180019BE1
0x180019a43  cmp     dword ptr [rax+28h], 2
0x180019a47  jnz     loc_180019AE2
0x180019a4d  lea     r8, [rsp+0A8h+arg_8]; unsigned __int8 *
0x180019a55  mov     [rsp+0A8h+arg_8], sil
0x180019a5d  mov     rdx, rbx; struct _SASL_CONTEXT *
0x180019a60  mov     rcx, r14; struct _SecBufferDesc *
0x180019a63  call    ?SaslCrackCookie@@YAJPEAU_SecBufferDesc@@PEAU_SASL_CONTEXT@@PEAE@Z; SaslCrackCookie(_SecBufferDesc *,_SASL_CONTEXT *,uchar *)
0x180019a68  test    eax, eax
0x180019a6a  js      short loc_180019AB8
0x180019a6c  mov     r8b, [rsp+0A8h+arg_8]
0x180019a74  mov     ecx, esi
0x180019a76  test    r8b, 2
0x180019a7a  jz      short loc_180019A8E
0x180019a7c  mov     eax, [rbx+34h]
0x180019a7f  mov     edx, 2000Ch
0x180019a84  and     eax, edx
0x180019a86  jz      short loc_180019A8E
0x180019a88  test    [rbx+30h], edx
0x180019a8b  cmovnz  ecx, eax
0x180019a8e  mov     edx, [rbx+34h]
0x180019a91  test    dl, 10h
0x180019a94  setnz   al
0x180019a97  shr     r8b, 2
0x180019a9b  and     al, r8b
0x180019a9e  test    al, 1
0x180019aa0  jz      short loc_180019AAB
0x180019aa2  test    byte ptr [rbx+30h], 10h
0x180019aa6  jz      short loc_180019AAB
0x180019aa8  or      ecx, 10h
0x180019aab  and     edx, 0FFFDFFE3h
0x180019ab1  mov     eax, esi
0x180019ab3  or      edx, ecx
0x180019ab5  mov     [rbx+34h], edx
0x180019ab8  mov     edx, [rbx+34h]
0x180019abb  mov     rcx, [rsp+0A8h+pfContextAttr]
0x180019ac3  mov     [rcx], edx
0x180019ac5  mov     rdx, [rsp+0A8h+ptsExpiry]
0x180019acd  test    rdx, rdx
0x180019ad0  jz      loc_180019BE1
0x180019ad6  mov     rcx, [rbx+20h]
0x180019ada  mov     [rdx], rcx
0x180019add  jmp     loc_180019BE1
0x180019ae2  mov     r12, [rsp+0A8h+pfContextAttr]
0x180019aea  lea     rax, [rsp+0A8h+var_58]
0x180019aef  mov     rbp, [rsp+0A8h+pOutput]
0x180019af7  mov     r9d, r15d
0x180019afa  mov     rsi, [rsp+0A8h+phNewContext]
0x180019b02  or      r9d, 20010h; fContextReq
0x180019b09  mov     [rsp+0A8h+var_68], rax; ptsExpiry
0x180019b0e  mov     r8, r14; pInput
0x180019b11  mov     eax, [rsp+0A8h+TargetDataRep]
0x180019b18  mov     rdx, rdi; phContext
0x180019b1b  mov     [rsp+0A8h+var_70], r12; pfContextAttr
0x180019b20  mov     rcx, r13; phCredential
0x180019b23  mov     [rsp+0A8h+var_78], rbp; pOutput
0x180019b28  mov     [rsp+0A8h+var_80], rsi; phNewContext
0x180019b2d  mov     [rsp+0A8h+var_88], eax; TargetDataRep
0x180019b31  call    AcceptSecurityContext
0x180019b36  mov     edi, eax
0x180019b38  test    eax, eax
0x180019b3a  js      loc_180019BD2
0x180019b40  test    rbx, rbx
0x180019b43  jnz     short loc_180019B6A
0x180019b45  mov     rcx, rsi; struct _SecHandle *
0x180019b48  call    ?SaslCreateContext@@YAPEAU_SASL_CONTEXT@@PEAU_SecHandle@@@Z; SaslCreateContext(_SecHandle *)
0x180019b4d  mov     rbx, rax
0x180019b50  test    rax, rax
0x180019b53  jz      short loc_180019B5B
0x180019b55  mov     [rax+30h], r15d
0x180019b59  jmp     short loc_180019B72
0x180019b5b  mov     rcx, rsi; phContext
0x180019b5e  call    DeleteSecurityContext
0x180019b63  mov     edi, 80090300h
0x180019b68  jmp     short loc_180019B72
0x180019b6a  movups  xmm0, xmmword ptr [rsi]
0x180019b6d  movdqu  xmmword ptr [rbx+10h], xmm0
0x180019b72  test    edi, edi
0x180019b74  jnz     short loc_180019BDF
0x180019b76  mov     eax, [r12]
0x180019b7a  mov     rcx, [rsp+0A8h+ptsExpiry]
0x180019b82  mov     [rbx+34h], eax
0x180019b85  mov     rax, qword ptr [rsp+0A8h+var_58]
0x180019b8a  mov     [rbx+20h], rax
0x180019b8e  test    rcx, rcx
0x180019b91  jz      short loc_180019B9B
0x180019b93  mov     rax, qword ptr [rsp+0A8h+var_58]
0x180019b98  mov     [rcx], rax
0x180019b9b  mov     rcx, rbp; struct _SecBufferDesc *
0x180019b9e  call    ?SaslLocateBuffer@@YAPEAU_SecBuffer@@PEAU_SecBufferDesc@@K@Z; SaslLocateBuffer(_SecBufferDesc *,ulong)
0x180019ba3  test    rax, rax
0x180019ba6  jz      short loc_180019BB6
0x180019ba8  mov     edi, 90312h
0x180019bad  mov     dword ptr [rbx+28h], 1
0x180019bb4  jmp     short loc_180019BDF
0x180019bb6  mov     rdx, rbx; struct _SASL_CONTEXT *
0x180019bb9  mov     dword ptr [rbx+28h], 2
0x180019bc0  call    ?SaslBuildServerCookie@@YAJPEAU_SecBufferDesc@@PEAU_SASL_CONTEXT@@@Z; SaslBuildServerCookie(_SecBufferDesc *,_SASL_CONTEXT *)
0x180019bc5  mov     edi, eax
0x180019bc7  test    eax, eax
0x180019bc9  js      short loc_180019BDF
0x180019bcb  mov     edi, 90312h
0x180019bd0  jmp     short loc_180019BDF
0x180019bd2  test    rbx, rbx
0x180019bd5  jz      short loc_180019BDF
0x180019bd7  mov     rcx, rbx; struct _SASL_CONTEXT *
0x180019bda  call    ?SaslDeleteContext@@YAXPEAU_SASL_CONTEXT@@@Z; SaslDeleteContext(_SASL_CONTEXT *)
0x180019bdf  mov     eax, edi
0x180019be1  add     rsp, 68h
0x180019be5  pop     r15
0x180019be7  pop     r14
0x180019be9  pop     r13
0x180019beb  pop     r12
0x180019bed  pop     rdi
0x180019bee  pop     rsi
0x180019bef  pop     rbp
0x180019bf0  pop     rbx
0x180019bf1  retn
```
