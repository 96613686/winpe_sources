# WapAuthDigestAuth

- ea: `0x18008c7f0`
- end: `0x18008ca70`
- name: `WapAuthDigestAuth`
- size: `640`
- prototype: `__int64 __fastcall(__int64, __int64, SEC_CHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18008c4e0`

## callees

- `0x180013820`
- `0x180068cf8`
- `0x1800722f0`
- `0x18008c7f0`
- `0x18008ca78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c861`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c861`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ca12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ca12`
- `SspiCli!InitializeSecurityContextA` at `0x18008c9ee`
- `SspiCli!InitializeSecurityContextA` at `0x18008c9ee`
- `SspiCli!DeleteSecurityContext` at `0x18008c884`
- `SspiCli!DeleteSecurityContext` at `0x18008c884`

## pseudocode

```c
__int64 __fastcall WapAuthDigestAuth(__int64 a1, __int64 a2, SEC_CHAR *a3, _DWORD *a4)
{
  __int64 v4; // r15
  __int64 v5; // rsi
  SEC_CHAR *v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // eax
  SEC_CHAR *v12; // r14
  unsigned int v13; // esi
  int *v14; // rdx
  _DWORD *v15; // rbx
  unsigned int v16; // r9d
  SECURITY_STATUS v17; // eax
  char v19[8]; // [rsp+60h] [rbp-A0h] BYREF
  SEC_CHAR *v20; // [rsp+68h] [rbp-98h] BYREF
  SEC_CHAR *pszTargetName; // [rsp+70h] [rbp-90h] BYREF
  SEC_CHAR *v22; // [rsp+78h] [rbp-88h] BYREF
  _DWORD *v23; // [rsp+80h] [rbp-80h]
  struct _SecBufferDesc pInput; // [rsp+88h] [rbp-78h] BYREF
  __int128 v25; // [rsp+98h] [rbp-68h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int pfContextAttr; // [rsp+B8h] [rbp-48h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v29[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v30; // [rsp+D8h] [rbp-28h]
  int v31; // [rsp+E0h] [rbp-20h]
  int v32; // [rsp+E4h] [rbp-1Ch]
  __int64 v33; // [rsp+E8h] [rbp-18h]
  int v34; // [rsp+F0h] [rbp-10h]
  int v35; // [rsp+F4h] [rbp-Ch]
  __int64 v36; // [rsp+F8h] [rbp-8h]
  int v37; // [rsp+100h] [rbp+0h]
  int v38; // [rsp+104h] [rbp+4h]
  SEC_CHAR *v39; // [rsp+108h] [rbp+8h]
  int v40; // [rsp+110h] [rbp+10h]
  int v41; // [rsp+114h] [rbp+14h]
  __int64 v42; // [rsp+118h] [rbp+18h]

  v4 = *(_QWORD *)(a1 + 24);
  v5 = *(_QWORD *)(a1 + 48);
  v23 = a4;
  v20 = a3;
  pfContextAttr = 0;
  pInput = 0;
  ptsExpiry.QuadPart = 0;
  v7 = 0;
  pOutput = 0;
  pszTargetName = 0;
  v25 = 0;
  v22 = 0;
  v19[0] = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 40));
  v8 = -1;
  if ( *(_QWORD *)(v4 + 88) != -1 && *(_QWORD *)(v4 + 96) != -1 )
  {
    DeleteSecurityContext((PCtxtHandle)(v4 + 88));
    *(_QWORD *)(v4 + 96) = -1;
    *(_QWORD *)(v4 + 88) = -1;
  }
  v9 = *(_QWORD *)(a2 + 16);
  pInput.pBuffers = (PSecBuffer)v29;
  pInput.ulVersion = 0;
  pInput.cBuffers = 4;
  v29[1] = 2;
  v29[0] = *(_DWORD *)(v5 + 24);
  v30 = *(_QWORD *)(v5 + 16);
  v10 = -1;
  v32 = 3;
  do
    ++v10;
  while ( *(_BYTE *)(v9 + v10) );
  v33 = v9;
  v35 = 3;
  v31 = v10;
  v34 = 0;
  v36 = 0;
  v11 = WaAuthGenerateSpn(a2, &v22, v19);
  v12 = v22;
  v13 = v11;
  if ( !v11 )
  {
    v38 = 16;
    if ( !v19[0] )
      LODWORD(v7) = 0x20000000;
    v39 = v22;
    do
      ++v8;
    while ( *(_WORD *)&v22[2 * v8] );
    v14 = *(int **)(a2 + 144);
    v37 = 2 * v8 + 2;
    if ( v14 )
    {
      pInput.cBuffers = 5;
      v41 = 14;
      v42 = *((_QWORD *)v14 + 1);
      v40 = *v14;
    }
    v15 = v23;
    pOutput.pBuffers = (PSecBuffer)&v25;
    pOutput.ulVersion = 0;
    pOutput.cBuffers = 1;
    LODWORD(v25) = *v23;
    *((_QWORD *)&v25 + 1) = v20;
    DWORD1(v25) = 2;
    v13 = WapAuthDigestConstructUri(a2, &pszTargetName, 0);
    if ( v13 )
    {
      v7 = pszTargetName;
    }
    else
    {
      v16 = (unsigned int)v7 | 0x10000000;
      v7 = pszTargetName;
      v17 = InitializeSecurityContextA(
              (PCredHandle)(v4 + 24),
              0,
              pszTargetName,
              v16,
              0,
              0x10u,
              &pInput,
              0,
              (PCtxtHandle)(v4 + 88),
              &pOutput,
              &pfContextAttr,
              &ptsExpiry);
      if ( v17 )
        v13 = v17;
      else
        *v15 = v25;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 40));
  if ( v12 )
  {
    v20 = v12;
    WxFreeHeapEx(&v20);
  }
  if ( v7 )
  {
    v20 = v7;
    WxFreeHeapEx(&v20);
  }
  return v13;
}

```

## disassembly

```asm
0x18008c7f0  mov     [rsp-8+arg_10], rbx
0x18008c7f5  push    rbp
0x18008c7f6  push    rsi
0x18008c7f7  push    rdi
0x18008c7f8  push    r12
0x18008c7fa  push    r13
0x18008c7fc  push    r14
0x18008c7fe  push    r15
0x18008c800  lea     rbp, [rsp-30h]
0x18008c805  sub     rsp, 130h
0x18008c80c  mov     rax, cs:__security_cookie
0x18008c813  xor     rax, rsp
0x18008c816  mov     [rbp+60h+var_40], rax
0x18008c81a  mov     r15, [rcx+18h]
0x18008c81e  xor     r14d, r14d
0x18008c821  mov     rsi, [rcx+30h]
0x18008c825  xorps   xmm0, xmm0
0x18008c828  xorps   xmm1, xmm1
0x18008c82b  mov     [rbp+60h+var_E0], r9
0x18008c82f  mov     [rsp+160h+var_F8], r8
0x18008c834  mov     r13, rdx
0x18008c837  lea     rcx, [r15+28h]; lpCriticalSection
0x18008c83b  mov     [rbp+60h+var_A8], r14d
0x18008c83f  movups  xmmword ptr [rbp+60h+var_D8.ulVersion], xmm0
0x18008c843  mov     qword ptr [rbp+60h+var_A0], r14
0x18008c847  mov     edi, r14d
0x18008c84a  movups  xmmword ptr [rbp+60h+var_B8.ulVersion], xmm1
0x18008c84e  mov     [rsp+160h+pszTargetName], r14
0x18008c853  movups  [rbp+60h+var_C8], xmm0
0x18008c857  mov     [rsp+160h+var_E8], r14
0x18008c85c  mov     [rsp+160h+var_100], r14b
0x18008c861  call    cs:__imp_EnterCriticalSection
0x18008c868  nop     dword ptr [rax+rax+00h]
0x18008c86d  lea     r12, [r15+58h]
0x18008c871  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008c875  cmp     [r12], rbx
0x18008c879  jz      short loc_18008C898
0x18008c87b  cmp     [r15+60h], rbx
0x18008c87f  jz      short loc_18008C898
0x18008c881  mov     rcx, r12; phContext
0x18008c884  call    cs:__imp_DeleteSecurityContext
0x18008c88b  nop     dword ptr [rax+rax+00h]
0x18008c890  mov     [r15+60h], rbx
0x18008c894  mov     [r12], rbx
0x18008c898  mov     rcx, [r13+10h]
0x18008c89c  lea     rax, [rbp+60h+var_90]
0x18008c8a0  mov     [rbp+60h+var_D8.pBuffers], rax
0x18008c8a4  mov     edx, 3
0x18008c8a9  mov     [rbp+60h+var_D8.ulVersion], r14d
0x18008c8ad  mov     [rbp+60h+var_D8.cBuffers], 4
0x18008c8b4  mov     [rbp+60h+var_8C], 2
0x18008c8bb  mov     eax, [rsi+18h]
0x18008c8be  mov     [rbp+60h+var_90], eax
0x18008c8c1  mov     rax, [rsi+10h]
0x18008c8c5  mov     [rbp+60h+var_88], rax
0x18008c8c9  mov     rax, rbx
0x18008c8cc  mov     [rbp+60h+var_7C], edx
0x18008c8cf  inc     rax
0x18008c8d2  cmp     [rcx+rax], r14b
0x18008c8d6  jnz     short loc_18008C8CF
0x18008c8d8  mov     [rbp+60h+var_78], rcx
0x18008c8dc  lea     r8, [rsp+160h+var_100]
0x18008c8e1  mov     [rbp+60h+var_6C], edx
0x18008c8e4  mov     rcx, r13
0x18008c8e7  lea     rdx, [rsp+160h+var_E8]
0x18008c8ec  mov     [rbp+60h+var_80], eax
0x18008c8ef  mov     [rbp+60h+var_70], r14d
0x18008c8f3  mov     [rbp+60h+var_68], r14
0x18008c8f7  call    WaAuthGenerateSpn
0x18008c8fc  mov     r14, [rsp+160h+var_E8]
0x18008c901  xor     ecx, ecx
0x18008c903  mov     esi, eax
0x18008c905  test    eax, eax
0x18008c907  jnz     loc_18008CA0E
0x18008c90d  cmp     [rsp+160h+var_100], cl
0x18008c911  mov     eax, 20000000h
0x18008c916  mov     [rbp+60h+var_5C], 10h
0x18008c91d  cmovz   edi, eax
0x18008c920  mov     [rbp+60h+var_58], r14
0x18008c924  inc     rbx
0x18008c927  cmp     [r14+rbx*2], cx
0x18008c92c  jnz     short loc_18008C924
0x18008c92e  mov     rdx, [r13+90h]
0x18008c935  lea     eax, ds:2[rbx*2]
0x18008c93c  mov     [rbp+60h+var_60], eax
0x18008c93f  test    rdx, rdx
0x18008c942  jz      short loc_18008C95F
0x18008c944  mov     [rbp+60h+var_D8.cBuffers], 5
0x18008c94b  mov     [rbp+60h+var_4C], 0Eh
0x18008c952  mov     rax, [rdx+8]
0x18008c956  mov     [rbp+60h+var_48], rax
0x18008c95a  mov     eax, [rdx]
0x18008c95c  mov     [rbp+60h+var_50], eax
0x18008c95f  mov     rbx, [rbp+60h+var_E0]
0x18008c963  lea     rax, [rbp+60h+var_C8]
0x18008c967  mov     [rbp+60h+var_B8.pBuffers], rax
0x18008c96b  lea     rdx, [rsp+160h+pszTargetName]
0x18008c970  mov     [rbp+60h+var_B8.ulVersion], ecx
0x18008c973  xor     r8d, r8d
0x18008c976  mov     rcx, r13
0x18008c979  mov     [rbp+60h+var_B8.cBuffers], 1
0x18008c980  mov     eax, [rbx]
0x18008c982  mov     dword ptr [rbp+60h+var_C8], eax
0x18008c985  mov     rax, [rsp+160h+var_F8]
0x18008c98a  mov     qword ptr [rbp+60h+var_C8+8], rax
0x18008c98e  mov     dword ptr [rbp+60h+var_C8+4], 2
0x18008c995  call    WapAuthDigestConstructUri
0x18008c99a  mov     esi, eax
0x18008c99c  test    eax, eax
0x18008c99e  jnz     short loc_18008CA09
0x18008c9a0  lea     rax, [rbp+60h+var_A0]
0x18008c9a4  bts     edi, 1Ch
0x18008c9a8  mov     [rsp+160h+ptsExpiry], rax; ptsExpiry
0x18008c9ad  lea     rcx, [r15+18h]; phCredential
0x18008c9b1  lea     rax, [rbp+60h+var_A8]
0x18008c9b5  mov     r9d, edi; fContextReq
0x18008c9b8  mov     rdi, [rsp+160h+pszTargetName]
0x18008c9bd  xor     edx, edx; phContext
0x18008c9bf  mov     [rsp+160h+pfContextAttr], rax; pfContextAttr
0x18008c9c4  mov     r8, rdi; pszTargetName
0x18008c9c7  lea     rax, [rbp+60h+var_B8]
0x18008c9cb  mov     [rsp+160h+pOutput], rax; pOutput
0x18008c9d0  lea     rax, [rbp+60h+var_D8]
0x18008c9d4  mov     [rsp+160h+phNewContext], r12; phNewContext
0x18008c9d9  mov     [rsp+160h+Reserved2], esi; Reserved2
0x18008c9dd  mov     [rsp+160h+pInput], rax; pInput
0x18008c9e2  mov     [rsp+160h+TargetDataRep], 10h; TargetDataRep
0x18008c9ea  mov     [rsp+160h+Reserved1], esi; Reserved1
0x18008c9ee  call    cs:__imp_InitializeSecurityContextA
0x18008c9f5  nop     dword ptr [rax+rax+00h]
0x18008c9fa  test    eax, eax
0x18008c9fc  jz      short loc_18008CA02
0x18008c9fe  mov     esi, eax
0x18008ca00  jmp     short loc_18008CA0E
0x18008ca02  mov     eax, dword ptr [rbp+60h+var_C8]
0x18008ca05  mov     [rbx], eax
0x18008ca07  jmp     short loc_18008CA0E
0x18008ca09  mov     rdi, [rsp+160h+pszTargetName]
0x18008ca0e  lea     rcx, [r15+28h]; lpCriticalSection
0x18008ca12  call    cs:__imp_LeaveCriticalSection
0x18008ca19  nop     dword ptr [rax+rax+00h]
0x18008ca1e  test    r14, r14
0x18008ca21  jz      short loc_18008CA32
0x18008ca23  lea     rcx, [rsp+160h+var_F8]
0x18008ca28  mov     [rsp+160h+var_F8], r14
0x18008ca2d  call    WxFreeHeapEx
0x18008ca32  test    rdi, rdi
0x18008ca35  jz      short loc_18008CA46
0x18008ca37  lea     rcx, [rsp+160h+var_F8]
0x18008ca3c  mov     [rsp+160h+var_F8], rdi
0x18008ca41  call    WxFreeHeapEx
0x18008ca46  mov     eax, esi
0x18008ca48  mov     rcx, [rbp+60h+var_40]
0x18008ca4c  xor     rcx, rsp; StackCookie
0x18008ca4f  call    __security_check_cookie
0x18008ca54  mov     rbx, [rsp+160h+arg_10]
0x18008ca5c  add     rsp, 130h
0x18008ca63  pop     r15
0x18008ca65  pop     r14
0x18008ca67  pop     r13
0x18008ca69  pop     r12
0x18008ca6b  pop     rdi
0x18008ca6c  pop     rsi
0x18008ca6d  pop     rbp
0x18008ca6e  retn
```
