# CTokenActivation::TokenActivate(unsigned __int64)

- ea: `0x18003a800`
- end: `0x18003ac13`
- name: `?TokenActivate@CTokenActivation@@UEAAJ_K@Z`
- size: `1043`
- prototype: `__int64 __fastcall(CTokenActivation *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180003520`
- `0x180004288`
- `0x180037c68`
- `0x180038028`
- `0x180038eb8`
- `0x1800396c4`
- `0x180039bf8`
- `0x18003a474`
- `0x18003a800`
- `0x18003c506`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003abb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003abd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003abf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003abb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003abd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003abf3`
- `SLC!SLConsumeWindowsRight` at `0x18003aa0c`
- `SLC!SLConsumeWindowsRight` at `0x18003aa0c`
- `sppcext!SLSignTokenActivationChallenge` at `0x18003a9a8`
- `sppcext!SLSignTokenActivationChallenge` at `0x18003aa6d`
- `sppcext!SLSignTokenActivationChallenge` at `0x18003a9a8`
- `sppcext!SLSignTokenActivationChallenge` at `0x18003aa6d`
- `sppcext!SLGenerateTokenActivationChallenge` at `0x18003a87d`
- `sppcext!SLGenerateTokenActivationChallenge` at `0x18003a87d`
- `sppcext!SLDepositTokenActivationResponse` at `0x18003a9f4`
- `sppcext!SLDepositTokenActivationResponse` at `0x18003a9f4`

## pseudocode

```c
__int64 __fastcall CTokenActivation::TokenActivate(CTokenActivation *this, __int64 a2)
{
  char *v2; // r13
  int SmartCardCertificates; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // r15d
  int v9; // ecx
  __int64 v10; // rdx
  int v11; // esi
  CTokenActivation *v12; // rcx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  bool v20; // zf
  const struct _CERT_CONTEXT *v21; // rdx
  __int64 v22; // rax
  HLOCAL v23; // rcx
  int v24; // r14d
  int v25; // esi
  BOOL v26; // esi
  __int64 v27; // rcx
  size_t v28; // r8
  const void *v29; // rcx
  __int64 v30; // rdx
  HLOCAL v32; // [rsp+50h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-20h] BYREF
  HLOCAL v34[3]; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v35; // [rsp+C0h] [rbp+48h] BYREF
  int v36; // [rsp+C8h] [rbp+50h] BYREF
  int v37; // [rsp+D0h] [rbp+58h] BYREF
  int v38; // [rsp+D8h] [rbp+60h] BYREF

  v2 = (char *)this + 168;
  v35 = 0;
  *((_QWORD *)this + 23) = a2;
  v34[0] = 0;
  v32 = 0;
  hMem = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  *((_QWORD *)this + 20) = a2;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  SmartCardCertificates = SLGenerateTokenActivationChallenge(*((_QWORD *)this + 24), (char *)this + 200, &v35, v34);
  v5 = SmartCardCertificates;
  if ( SmartCardCertificates < 0 )
    goto LABEL_2;
  SmartCardCertificates = CTokenActivation::InitializeCertificates(this);
  v5 = SmartCardCertificates;
  if ( SmartCardCertificates < 0 )
    goto LABEL_2;
  v7 = *((_QWORD *)this + 28);
  v8 = 0;
  v9 = 0;
  if ( v7 )
  {
    LOBYTE(v9) = *(_DWORD *)v7 != 1;
    ++v9;
  }
  v10 = *((_QWORD *)this + 27);
  v11 = 0;
  if ( v10 )
  {
    LOBYTE(v11) = *(_DWORD *)v10 != 1;
    ++v11;
  }
  v12 = (CTokenActivation *)(unsigned int)(v11 + 2 * v9 + v9);
  if ( (_DWORD)v12 )
  {
    v13 = (_DWORD)v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( !v14 )
      {
        SmartCardCertificates = CTokenActivation::SetSelectedCert(this, 0);
        v5 = SmartCardCertificates;
        if ( SmartCardCertificates < 0 )
          goto LABEL_2;
        v8 = 1;
        goto LABEL_20;
      }
      v15 = v14 - 1;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          v17 = v16 - 1;
          if ( v17 )
          {
            v18 = v17 - 1;
            if ( !v18 || (v19 = v18 - 1) == 0 )
            {
LABEL_18:
              v21 = 0;
              goto LABEL_19;
            }
            goto LABEL_16;
          }
        }
      }
      SmartCardCertificates = CTokenActivation::SetSelectedCert(this, *(const struct _CERT_CONTEXT **)(v7 + 8));
      v5 = SmartCardCertificates;
      if ( SmartCardCertificates < 0 )
        goto LABEL_2;
      v24 = SLSignTokenActivationChallenge(*((_QWORD *)this + 30), v35, v34[0], v2, 0, &v37, &v32, &v36, &hMem);
      if ( v24 >= 0 )
        goto LABEL_20;
      if ( !v11 )
        goto LABEL_43;
      v25 = v11 - 1;
      if ( v25 )
      {
        v20 = v25 == 1;
LABEL_17:
        if ( !v20 )
          goto LABEL_20;
        goto LABEL_18;
      }
      v26 = 0;
      v27 = *(_QWORD *)(*((_QWORD *)this + 28) + 8LL);
      v28 = *(unsigned int *)(v27 + 16);
      if ( (_DWORD)v28
        && (v29 = *(const void **)(v27 + 8)) != 0
        && (v30 = *(_QWORD *)(*((_QWORD *)this + 27) + 8LL), *(_DWORD *)(v30 + 16))
        && *(_QWORD *)(v30 + 8) )
      {
        v5 = 0;
        if ( (_DWORD)v28 == *(_DWORD *)(v30 + 16) )
          v26 = memcmp_0(v29, *(const void **)(v30 + 8), v28) == 0;
      }
      else
      {
        v5 = -2147024883;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942413LL);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
      if ( (v5 & 0x80000000) != 0 )
      {
        v6 = v5;
        goto LABEL_57;
      }
      if ( v26 )
      {
LABEL_43:
        v5 = v24;
        v6 = (unsigned int)v24;
        goto LABEL_57;
      }
      v10 = *((_QWORD *)this + 27);
    }
  }
  else
  {
    SmartCardCertificates = CTokenActivation::DetectSmartCard(v12, &v38);
    v5 = SmartCardCertificates;
    if ( SmartCardCertificates < 0 )
      goto LABEL_2;
    if ( v38 )
      goto LABEL_56;
    SmartCardCertificates = CTokenActivation::PromptSmartCard(this);
    v5 = SmartCardCertificates;
    if ( SmartCardCertificates < 0 )
      goto LABEL_2;
    SmartCardCertificates = CTokenActivation::GetSmartCardCertificates(this);
    v5 = SmartCardCertificates;
    if ( SmartCardCertificates < 0 )
      goto LABEL_2;
    v10 = *((_QWORD *)this + 28);
    if ( !v10 || (*(_DWORD *)v10 != 1) == -1 )
      goto LABEL_56;
    v19 = *(_DWORD *)v10 != 1;
    if ( *(_DWORD *)v10 != 1 )
    {
LABEL_16:
      v20 = v19 == 1;
      goto LABEL_17;
    }
  }
  v21 = *(const struct _CERT_CONTEXT **)(v10 + 8);
LABEL_19:
  SmartCardCertificates = CTokenActivation::SetSelectedCert(this, v21);
  v5 = SmartCardCertificates;
  if ( SmartCardCertificates < 0 )
    goto LABEL_2;
LABEL_20:
  v22 = *((_QWORD *)this + 30);
  if ( !v22 )
  {
    SmartCardCertificates = CTokenActivation::ThrowCertChooser(this, v8);
    v5 = SmartCardCertificates;
    if ( SmartCardCertificates < 0 )
      goto LABEL_2;
    v22 = *((_QWORD *)this + 30);
    if ( !v22 )
    {
LABEL_56:
      v6 = 3221549835LL;
      v5 = -1073417461;
      goto LABEL_57;
    }
  }
  v23 = v32;
  if ( v32 )
    goto LABEL_26;
  SmartCardCertificates = SLSignTokenActivationChallenge(v22, v35, v34[0], v2, 0, &v37, &v32, &v36, &hMem);
  v5 = SmartCardCertificates;
  if ( SmartCardCertificates >= 0 )
  {
    v23 = v32;
LABEL_26:
    SmartCardCertificates = SLDepositTokenActivationResponse(
                              *((_QWORD *)this + 24),
                              (char *)this + 200,
                              v35,
                              v34[0],
                              v37,
                              v23,
                              v36,
                              hMem);
    v5 = SmartCardCertificates;
    if ( SmartCardCertificates >= 0 )
    {
      SLConsumeWindowsRight(0);
      goto LABEL_58;
    }
  }
LABEL_2:
  v6 = (unsigned int)SmartCardCertificates;
LABEL_57:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
LABEL_58:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v32 )
  {
    LocalFree(v32);
    v32 = 0;
  }
  if ( v34[0] )
    LocalFree(v34[0]);
  return v5;
}

```

## disassembly

```asm
0x18003a800  push    rbp
0x18003a802  push    rbx
0x18003a803  push    rsi
0x18003a804  push    rdi
0x18003a805  push    r12
0x18003a807  push    r13
0x18003a809  push    r14
0x18003a80b  push    r15
0x18003a80d  mov     rbp, rsp
0x18003a810  sub     rsp, 78h
0x18003a814  lea     r13, [rcx+0A8h]
0x18003a81b  mov     [rbp+arg_0], 0
0x18003a822  mov     [r13+10h], rdx
0x18003a826  mov     rdi, rcx
0x18003a829  mov     [rbp+var_18], 0
0x18003a831  mov     [rbp+var_28], 0
0x18003a839  mov     [rbp+hMem], 0
0x18003a841  mov     [rbp+arg_18], 0
0x18003a848  mov     [rbp+arg_10], 0
0x18003a84f  mov     [rbp+arg_8], 0
0x18003a856  mov     [rcx+0A0h], rdx
0x18003a85d  xor     ecx, ecx
0x18003a85f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003a864  mov     rcx, [rdi+0C0h]
0x18003a86b  lea     r12, [rdi+0C8h]
0x18003a872  mov     rdx, r12
0x18003a875  lea     r9, [rbp+var_18]
0x18003a879  lea     r8, [rbp+arg_0]
0x18003a87d  call    cs:__imp_SLGenerateTokenActivationChallenge
0x18003a884  nop     dword ptr [rax+rax+00h]
0x18003a889  mov     ebx, eax
0x18003a88b  test    eax, eax
0x18003a88d  jns     short loc_18003A896
0x18003a88f  mov     ecx, eax
0x18003a891  jmp     loc_18003ABA4
0x18003a896  mov     rcx, rdi; this
0x18003a899  call    ?InitializeCertificates@CTokenActivation@@IEAAJXZ; CTokenActivation::InitializeCertificates(void)
0x18003a89e  mov     ebx, eax
0x18003a8a0  test    eax, eax
0x18003a8a2  js      short loc_18003A88F
0x18003a8a4  mov     r8, [rdi+0E0h]
0x18003a8ab  xor     r15d, r15d
0x18003a8ae  xor     ecx, ecx
0x18003a8b0  lea     r14d, [r15+1]
0x18003a8b4  test    r8, r8
0x18003a8b7  jz      short loc_18003A8C2
0x18003a8b9  cmp     [r8], r14d
0x18003a8bc  setnz   cl
0x18003a8bf  add     ecx, r14d
0x18003a8c2  mov     rdx, [rdi+0D8h]
0x18003a8c9  xor     esi, esi
0x18003a8cb  test    rdx, rdx
0x18003a8ce  jz      short loc_18003A8DA
0x18003a8d0  cmp     [rdx], r14d
0x18003a8d3  setnz   sil
0x18003a8d7  add     esi, r14d
0x18003a8da  lea     eax, [rsi+rcx*2]
0x18003a8dd  add     ecx, eax; this
0x18003a8df  jz      loc_18003AB3D
0x18003a8e5  sub     ecx, r14d
0x18003a8e8  jz      loc_18003AB18
0x18003a8ee  sub     ecx, r14d
0x18003a8f1  jz      loc_18003AB21
0x18003a8f7  sub     ecx, r14d
0x18003a8fa  jz      loc_18003AA1D
0x18003a900  sub     ecx, r14d
0x18003a903  jz      loc_18003AA1D
0x18003a909  sub     ecx, r14d
0x18003a90c  jz      loc_18003AA1D
0x18003a912  sub     ecx, r14d
0x18003a915  jz      short loc_18003A921
0x18003a917  sub     ecx, r14d
0x18003a91a  jz      short loc_18003A921
0x18003a91c  cmp     ecx, r14d
0x18003a91f  jnz     short loc_18003A935
0x18003a921  xor     edx, edx; struct _CERT_CONTEXT *
0x18003a923  mov     rcx, rdi; this
0x18003a926  call    ?SetSelectedCert@CTokenActivation@@IEAAJPEBU_CERT_CONTEXT@@@Z; CTokenActivation::SetSelectedCert(_CERT_CONTEXT const *)
0x18003a92b  mov     ebx, eax
0x18003a92d  test    eax, eax
0x18003a92f  js      loc_18003A88F
0x18003a935  mov     rax, [rdi+0F0h]
0x18003a93c  test    rax, rax
0x18003a93f  jnz     short loc_18003A966
0x18003a941  mov     edx, r15d; int
0x18003a944  mov     rcx, rdi; this
0x18003a947  call    ?ThrowCertChooser@CTokenActivation@@IEAAJH@Z; CTokenActivation::ThrowCertChooser(int)
0x18003a94c  mov     ebx, eax
0x18003a94e  test    eax, eax
0x18003a950  js      loc_18003A88F
0x18003a956  mov     rax, [rdi+0F0h]
0x18003a95d  test    rax, rax
0x18003a960  jz      loc_18003AB9D
0x18003a966  mov     rcx, [rbp+var_28]
0x18003a96a  test    rcx, rcx
0x18003a96d  jnz     short loc_18003A9C2
0x18003a96f  mov     r8, [rbp+var_18]
0x18003a973  lea     rcx, [rbp+hMem]
0x18003a977  mov     edx, [rbp+arg_0]
0x18003a97a  mov     r9, r13
0x18003a97d  mov     [rsp+78h+var_38], rcx
0x18003a982  lea     rcx, [rbp+arg_8]
0x18003a986  mov     [rsp+78h+var_40], rcx
0x18003a98b  lea     rcx, [rbp+var_28]
0x18003a98f  mov     [rsp+78h+var_48], rcx
0x18003a994  lea     rcx, [rbp+arg_10]
0x18003a998  mov     [rsp+78h+var_50], rcx
0x18003a99d  mov     rcx, rax
0x18003a9a0  mov     [rsp+78h+var_58], 0
0x18003a9a8  call    cs:__imp_SLSignTokenActivationChallenge
0x18003a9af  nop     dword ptr [rax+rax+00h]
0x18003a9b4  mov     ebx, eax
0x18003a9b6  test    eax, eax
0x18003a9b8  js      loc_18003A88F
0x18003a9be  mov     rcx, [rbp+var_28]
0x18003a9c2  mov     rax, [rbp+hMem]
0x18003a9c6  mov     rdx, r12
0x18003a9c9  mov     r10d, [rbp+arg_8]
0x18003a9cd  mov     r11d, [rbp+arg_10]
0x18003a9d1  mov     r9, [rbp+var_18]
0x18003a9d5  mov     r8d, [rbp+arg_0]
0x18003a9d9  mov     [rsp+78h+var_40], rax
0x18003a9de  mov     dword ptr [rsp+78h+var_48], r10d
0x18003a9e3  mov     [rsp+78h+var_50], rcx
0x18003a9e8  mov     rcx, [rdi+0C0h]
0x18003a9ef  mov     [rsp+78h+var_58], r11d
0x18003a9f4  call    cs:__imp_SLDepositTokenActivationResponse
0x18003a9fb  nop     dword ptr [rax+rax+00h]
0x18003aa00  mov     ebx, eax
0x18003aa02  test    eax, eax
0x18003aa04  js      loc_18003A88F
0x18003aa0a  xor     ecx, ecx
0x18003aa0c  call    cs:__imp_SLConsumeWindowsRight
0x18003aa13  nop     dword ptr [rax+rax+00h]
0x18003aa18  jmp     loc_18003ABA9
0x18003aa1d  mov     rdx, [r8+8]; struct _CERT_CONTEXT *
0x18003aa21  mov     rcx, rdi; this
0x18003aa24  call    ?SetSelectedCert@CTokenActivation@@IEAAJPEBU_CERT_CONTEXT@@@Z; CTokenActivation::SetSelectedCert(_CERT_CONTEXT const *)
0x18003aa29  mov     ebx, eax
0x18003aa2b  test    eax, eax
0x18003aa2d  js      loc_18003A88F
0x18003aa33  mov     r8, [rbp+var_18]
0x18003aa37  lea     rax, [rbp+hMem]
0x18003aa3b  mov     edx, [rbp+arg_0]
0x18003aa3e  mov     r9, r13
0x18003aa41  mov     rcx, [rdi+0F0h]
0x18003aa48  mov     [rsp+78h+var_38], rax
0x18003aa4d  lea     rax, [rbp+arg_8]
0x18003aa51  mov     [rsp+78h+var_40], rax
0x18003aa56  lea     rax, [rbp+var_28]
0x18003aa5a  mov     [rsp+78h+var_48], rax
0x18003aa5f  lea     rax, [rbp+arg_10]
0x18003aa63  mov     [rsp+78h+var_50], rax
0x18003aa68  mov     [rsp+78h+var_58], r15d
0x18003aa6d  call    cs:__imp_SLSignTokenActivationChallenge
0x18003aa74  nop     dword ptr [rax+rax+00h]
0x18003aa79  mov     r14d, eax
0x18003aa7c  test    eax, eax
0x18003aa7e  jns     loc_18003A935
0x18003aa84  test    esi, esi
0x18003aa86  jz      short loc_18003AB06
0x18003aa88  sub     esi, 1
0x18003aa8b  jz      short loc_18003AA95
0x18003aa8d  cmp     esi, 1
0x18003aa90  jmp     loc_18003A91F
0x18003aa95  mov     rax, [rdi+0E0h]
0x18003aa9c  xor     esi, esi
0x18003aa9e  mov     rcx, [rax+8]
0x18003aaa2  mov     r8d, [rcx+10h]; Size
0x18003aaa6  test    r8d, r8d
0x18003aaa9  jz      short loc_18003AAE4
0x18003aaab  mov     rcx, [rcx+8]; Buf1
0x18003aaaf  test    rcx, rcx
0x18003aab2  jz      short loc_18003AAE4
0x18003aab4  mov     rax, [rdi+0D8h]
0x18003aabb  mov     rdx, [rax+8]
0x18003aabf  cmp     [rdx+10h], esi
0x18003aac2  jz      short loc_18003AAE4
0x18003aac4  cmp     [rdx+8], rsi
0x18003aac8  jz      short loc_18003AAE4
0x18003aaca  xor     ebx, ebx
0x18003aacc  cmp     r8d, [rdx+10h]
0x18003aad0  jnz     short loc_18003AAF0
0x18003aad2  mov     rdx, [rdx+8]; Buf2
0x18003aad6  call    memcmp_0
0x18003aadb  test    eax, eax
0x18003aadd  jnz     short loc_18003AAF0
0x18003aadf  lea     esi, [rbx+1]
0x18003aae2  jmp     short loc_18003AAF0
0x18003aae4  mov     ecx, 8007000Dh
0x18003aae9  mov     ebx, ecx
0x18003aaeb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003aaf0  mov     ecx, ebx
0x18003aaf2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003aaf7  test    ebx, ebx
0x18003aaf9  jns     short loc_18003AB02
0x18003aafb  mov     ecx, ebx
0x18003aafd  jmp     loc_18003ABA4
0x18003ab02  test    esi, esi
0x18003ab04  jz      short loc_18003AB11
0x18003ab06  mov     ebx, r14d
0x18003ab09  mov     ecx, r14d
0x18003ab0c  jmp     loc_18003ABA4
0x18003ab11  mov     rdx, [rdi+0D8h]
0x18003ab18  mov     rdx, [rdx+8]
0x18003ab1c  jmp     loc_18003A923
0x18003ab21  xor     edx, edx; struct _CERT_CONTEXT *
0x18003ab23  mov     rcx, rdi; this
0x18003ab26  call    ?SetSelectedCert@CTokenActivation@@IEAAJPEBU_CERT_CONTEXT@@@Z; CTokenActivation::SetSelectedCert(_CERT_CONTEXT const *)
0x18003ab2b  mov     ebx, eax
0x18003ab2d  test    eax, eax
0x18003ab2f  js      loc_18003A88F
0x18003ab35  mov     r15d, r14d
0x18003ab38  jmp     loc_18003A935
0x18003ab3d  lea     rdx, [rbp+arg_18]; int *
0x18003ab41  call    ?DetectSmartCard@CTokenActivation@@IEAAJPEAH@Z; CTokenActivation::DetectSmartCard(int *)
0x18003ab46  mov     ebx, eax
0x18003ab48  test    eax, eax
0x18003ab4a  js      loc_18003A88F
0x18003ab50  cmp     [rbp+arg_18], r15d
0x18003ab54  jnz     short loc_18003AB9D
0x18003ab56  mov     rcx, rdi; this
0x18003ab59  call    ?PromptSmartCard@CTokenActivation@@IEAAJXZ; CTokenActivation::PromptSmartCard(void)
0x18003ab5e  mov     ebx, eax
0x18003ab60  test    eax, eax
0x18003ab62  js      loc_18003A88F
0x18003ab68  mov     rcx, rdi; this
0x18003ab6b  call    ?GetSmartCardCertificates@CTokenActivation@@IEAAJXZ; CTokenActivation::GetSmartCardCertificates(void)
0x18003ab70  mov     ebx, eax
0x18003ab72  test    eax, eax
0x18003ab74  js      loc_18003A88F
0x18003ab7a  mov     rdx, [rdi+0E0h]
0x18003ab81  test    rdx, rdx
0x18003ab84  jz      short loc_18003AB9D
0x18003ab86  xor     ecx, ecx
0x18003ab88  cmp     [rdx], r14d
0x18003ab8b  setnz   cl
0x18003ab8e  add     ecx, r14d
0x18003ab91  jz      short loc_18003AB9D
0x18003ab93  sub     ecx, r14d
0x18003ab96  jz      short loc_18003AB18
0x18003ab98  jmp     loc_18003A91C
0x18003ab9d  mov     ecx, 0C004F30Bh
0x18003aba2  mov     ebx, ecx
0x18003aba4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003aba9  mov     ecx, ebx
0x18003abab  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003abb0  mov     rcx, [rbp+hMem]; hMem
0x18003abb4  test    rcx, rcx
0x18003abb7  jz      short loc_18003ABCD
0x18003abb9  call    cs:__imp_LocalFree
0x18003abc0  nop     dword ptr [rax+rax+00h]
0x18003abc5  mov     [rbp+hMem], 0
0x18003abcd  mov     rcx, [rbp+var_28]; hMem
0x18003abd1  test    rcx, rcx
0x18003abd4  jz      short loc_18003ABEA
0x18003abd6  call    cs:__imp_LocalFree
0x18003abdd  nop     dword ptr [rax+rax+00h]
0x18003abe2  mov     [rbp+var_28], 0
0x18003abea  mov     rcx, [rbp+var_18]; hMem
0x18003abee  test    rcx, rcx
0x18003abf1  jz      short loc_18003ABFF
0x18003abf3  call    cs:__imp_LocalFree
0x18003abfa  nop     dword ptr [rax+rax+00h]
0x18003abff  mov     eax, ebx
0x18003ac01  add     rsp, 78h
0x18003ac05  pop     r15
0x18003ac07  pop     r14
0x18003ac09  pop     r13
0x18003ac0b  pop     r12
0x18003ac0d  pop     rdi
0x18003ac0e  pop     rsi
0x18003ac0f  pop     rbx
0x18003ac10  pop     rbp
0x18003ac11  retn
```
