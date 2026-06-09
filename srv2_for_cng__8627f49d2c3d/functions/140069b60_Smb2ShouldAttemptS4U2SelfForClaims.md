# Smb2ShouldAttemptS4U2SelfForClaims

- ea: `0x140069b60`
- end: `0x140069d25`
- name: `Smb2ShouldAttemptS4U2SelfForClaims`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400921f0`

## callees

- `0x140015960`
- `0x1400224b8`
- `0x140069b60`
- `0x140077600`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140069c0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069c50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069ca7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069c0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069c50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069ca7`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140069d0c`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140069d0c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140069bc6`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140069bc6`
- `ntoskrnl!SeQueryInformationToken` at `0x140069be6`
- `ntoskrnl!SeQueryInformationToken` at `0x140069c2e`
- `ntoskrnl!SeQueryInformationToken` at `0x140069c86`
- `ntoskrnl!SeQueryInformationToken` at `0x140069be6`
- `ntoskrnl!SeQueryInformationToken` at `0x140069c2e`
- `ntoskrnl!SeQueryInformationToken` at `0x140069c86`
- `srvnet!SrvLibIsNetwork` at `0x140069b77`
- `srvnet!SrvLibIsNetwork` at `0x140069b77`
- `srvnet!SrvLibHasClaimsSentinel` at `0x140069cba`
- `srvnet!SrvLibHasClaimsSentinel` at `0x140069cba`

## pseudocode

```c
bool __fastcall Smb2ShouldAttemptS4U2SelfForClaims(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  PACCESS_TOKEN v6; // rax
  void *v7; // rsi
  NTSTATUS v8; // eax
  int v9; // ebx
  bool v10; // di
  bool v11; // bl
  PVOID TokenInformation; // [rsp+20h] [rbp-10h] BYREF
  PVOID P; // [rsp+28h] [rbp-8h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+70h] [rbp+40h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+78h] [rbp+48h] BYREF

  if ( (int)Smb2ImpersonateSecurityContext(a1) < 0 )
    return 0;
  if ( !(unsigned __int8)SrvLibIsNetwork(v2, v1, v3, v4)
    || (CopyOnOpen = 0,
        EffectiveOnly = 0,
        ImpersonationLevel = SecurityAnonymous,
        TokenInformation = 0,
        v6 = PsReferenceImpersonationToken(KeGetCurrentThread(), &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel),
        (v7 = v6) == 0) )
  {
    Smb2Revert();
    return 0;
  }
  v8 = SeQueryInformationToken(v6, TokenUserClaimAttributes, &TokenInformation);
  if ( v8 < 0 )
  {
    v10 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids,
        (unsigned int)v8);
    }
  }
  else
  {
    v9 = *((_DWORD *)TokenInformation + 1);
    ExFreePoolWithTag(TokenInformation, 0);
    TokenInformation = 0;
    if ( v9 || SeQueryInformationToken(v7, TokenDeviceClaimAttributes, &TokenInformation) < 0 )
    {
      v10 = v9 == 0;
    }
    else
    {
      v10 = 0;
      if ( !*((_DWORD *)TokenInformation + 1) )
        v10 = v9 == 0;
      ExFreePoolWithTag(TokenInformation, 0);
      TokenInformation = 0;
    }
    if ( v10 )
    {
      P = 0;
      if ( SeQueryInformationToken(v7, TokenDeviceGroups, &P) < 0 )
        goto LABEL_27;
      v11 = 0;
      if ( !*(_DWORD *)P )
        v11 = v10;
      ExFreePoolWithTag(P, 0);
      v10 = v11;
      if ( v11 )
      {
LABEL_27:
        if ( (unsigned __int8)SrvLibHasClaimsSentinel() )
          v10 = 0;
      }
    }
  }
  PsDereferenceImpersonationToken(v7);
  Smb2Revert();
  return v10;
}

```

## disassembly

```asm
0x140069b60  push    rbp
0x140069b62  push    rbx
0x140069b63  push    rsi
0x140069b64  push    rdi
0x140069b65  push    r14
0x140069b67  mov     rbp, rsp
0x140069b6a  sub     rsp, 30h
0x140069b6e  call    Smb2ImpersonateSecurityContext
0x140069b73  test    eax, eax
0x140069b75  js      short loc_140069B8C
0x140069b77  call    cs:__imp_SrvLibIsNetwork
0x140069b7e  nop     dword ptr [rax+rax+00h]
0x140069b83  test    al, al
0x140069b85  jnz     short loc_140069B9A
0x140069b87  call    Smb2Revert
0x140069b8c  xor     al, al
0x140069b8e  add     rsp, 30h
0x140069b92  pop     r14
0x140069b94  pop     rdi
0x140069b95  pop     rsi
0x140069b96  pop     rbx
0x140069b97  pop     rbp
0x140069b98  retn
0x140069b9a  mov     [rbp+CopyOnOpen], 0
0x140069b9e  lea     r9, [rbp+ImpersonationLevel]; ImpersonationLevel
0x140069ba2  mov     [rbp+EffectiveOnly], 0
0x140069ba6  lea     r8, [rbp+EffectiveOnly]; EffectiveOnly
0x140069baa  mov     [rbp+ImpersonationLevel], 0
0x140069bb1  lea     rdx, [rbp+CopyOnOpen]; CopyOnOpen
0x140069bb5  mov     [rbp+TokenInformation], 0
0x140069bbd  mov     rcx, gs:188h; Thread
0x140069bc6  call    cs:__imp_PsReferenceImpersonationToken
0x140069bcd  nop     dword ptr [rax+rax+00h]
0x140069bd2  mov     rsi, rax
0x140069bd5  test    rax, rax
0x140069bd8  jz      short loc_140069B87
0x140069bda  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140069bde  mov     edx, 21h ; '!'; TokenInformationClass
0x140069be3  mov     rcx, rax; Token
0x140069be6  call    cs:__imp_SeQueryInformationToken
0x140069bed  nop     dword ptr [rax+rax+00h]
0x140069bf2  mov     r9d, eax
0x140069bf5  test    eax, eax
0x140069bf7  js      loc_140069CCF
0x140069bfd  mov     rcx, [rbp+TokenInformation]; P
0x140069c01  mov     ebx, [rcx+4]
0x140069c04  test    ebx, ebx
0x140069c06  setz    r14b
0x140069c0a  xor     edx, edx; Tag
0x140069c0c  call    cs:__imp_ExFreePoolWithTag
0x140069c13  nop     dword ptr [rax+rax+00h]
0x140069c18  mov     [rbp+TokenInformation], 0
0x140069c20  test    ebx, ebx
0x140069c22  jnz     short loc_140069C66
0x140069c24  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140069c28  mov     rcx, rsi; Token
0x140069c2b  lea     edx, [rbx+22h]; TokenInformationClass
0x140069c2e  call    cs:__imp_SeQueryInformationToken
0x140069c35  nop     dword ptr [rax+rax+00h]
0x140069c3a  test    eax, eax
0x140069c3c  js      short loc_140069C66
0x140069c3e  mov     rcx, [rbp+TokenInformation]; P
0x140069c42  xor     edi, edi
0x140069c44  movzx   eax, r14b
0x140069c48  cmp     [rcx+4], edi
0x140069c4b  cmovbe  edi, eax
0x140069c4e  xor     edx, edx; Tag
0x140069c50  call    cs:__imp_ExFreePoolWithTag
0x140069c57  nop     dword ptr [rax+rax+00h]
0x140069c5c  mov     [rbp+TokenInformation], 0
0x140069c64  jmp     short loc_140069C69
0x140069c66  mov     dil, r14b
0x140069c69  test    dil, dil
0x140069c6c  jz      loc_140069D09
0x140069c72  lea     r8, [rbp+P]; TokenInformation
0x140069c76  mov     [rbp+P], 0
0x140069c7e  mov     edx, 25h ; '%'; TokenInformationClass
0x140069c83  mov     rcx, rsi; Token
0x140069c86  call    cs:__imp_SeQueryInformationToken
0x140069c8d  nop     dword ptr [rax+rax+00h]
0x140069c92  test    eax, eax
0x140069c94  js      short loc_140069CBA
0x140069c96  mov     rcx, [rbp+P]; P
0x140069c9a  xor     ebx, ebx
0x140069c9c  movzx   eax, dil
0x140069ca0  cmp     [rcx], ebx
0x140069ca2  cmovbe  ebx, eax
0x140069ca5  xor     edx, edx; Tag
0x140069ca7  call    cs:__imp_ExFreePoolWithTag
0x140069cae  nop     dword ptr [rax+rax+00h]
0x140069cb3  mov     dil, bl
0x140069cb6  test    bl, bl
0x140069cb8  jz      short loc_140069D09
0x140069cba  call    cs:__imp_SrvLibHasClaimsSentinel
0x140069cc1  nop     dword ptr [rax+rax+00h]
0x140069cc6  test    al, al
0x140069cc8  jz      short loc_140069D09
0x140069cca  xor     dil, dil
0x140069ccd  jmp     short loc_140069D09
0x140069ccf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140069cd6  lea     rax, WPP_GLOBAL_Control
0x140069cdd  mov     dil, 1
0x140069ce0  cmp     rcx, rax
0x140069ce3  jz      short loc_140069D09
0x140069ce5  test    dword ptr [rcx+2Ch], 20000h
0x140069cec  jz      short loc_140069D09
0x140069cee  cmp     [rcx+29h], dil
0x140069cf2  jb      short loc_140069D09
0x140069cf4  mov     rcx, [rcx+18h]
0x140069cf8  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x140069cff  mov     edx, 32h ; '2'
0x140069d04  call    WPP_SF_d
0x140069d09  mov     rcx, rsi; ImpersonationToken
0x140069d0c  call    cs:__imp_PsDereferenceImpersonationToken
0x140069d13  nop     dword ptr [rax+rax+00h]
0x140069d18  call    Smb2Revert
0x140069d1d  mov     al, dil
0x140069d20  jmp     loc_140069B8E
```
