# Smb2ShouldAttemptS4U2SelfForClaims

- ea: `0x140069bb0`
- end: `0x140069d75`
- name: `Smb2ShouldAttemptS4U2SelfForClaims`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140092240`

## callees

- `0x140015960`
- `0x1400224b8`
- `0x140069bb0`
- `0x140077650`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140069c5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069ca0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069cf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069c5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069ca0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069cf7`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140069d5c`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140069d5c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140069c16`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140069c16`
- `ntoskrnl!SeQueryInformationToken` at `0x140069c36`
- `ntoskrnl!SeQueryInformationToken` at `0x140069c7e`
- `ntoskrnl!SeQueryInformationToken` at `0x140069cd6`
- `ntoskrnl!SeQueryInformationToken` at `0x140069c36`
- `ntoskrnl!SeQueryInformationToken` at `0x140069c7e`
- `ntoskrnl!SeQueryInformationToken` at `0x140069cd6`
- `srvnet!SrvLibIsNetwork` at `0x140069bc7`
- `srvnet!SrvLibIsNetwork` at `0x140069bc7`
- `srvnet!SrvLibHasClaimsSentinel` at `0x140069d0a`
- `srvnet!SrvLibHasClaimsSentinel` at `0x140069d0a`

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
0x140069bb0  push    rbp
0x140069bb2  push    rbx
0x140069bb3  push    rsi
0x140069bb4  push    rdi
0x140069bb5  push    r14
0x140069bb7  mov     rbp, rsp
0x140069bba  sub     rsp, 30h
0x140069bbe  call    Smb2ImpersonateSecurityContext
0x140069bc3  test    eax, eax
0x140069bc5  js      short loc_140069BDC
0x140069bc7  call    cs:__imp_SrvLibIsNetwork
0x140069bce  nop     dword ptr [rax+rax+00h]
0x140069bd3  test    al, al
0x140069bd5  jnz     short loc_140069BEA
0x140069bd7  call    Smb2Revert
0x140069bdc  xor     al, al
0x140069bde  add     rsp, 30h
0x140069be2  pop     r14
0x140069be4  pop     rdi
0x140069be5  pop     rsi
0x140069be6  pop     rbx
0x140069be7  pop     rbp
0x140069be8  retn
0x140069bea  mov     [rbp+CopyOnOpen], 0
0x140069bee  lea     r9, [rbp+ImpersonationLevel]; ImpersonationLevel
0x140069bf2  mov     [rbp+EffectiveOnly], 0
0x140069bf6  lea     r8, [rbp+EffectiveOnly]; EffectiveOnly
0x140069bfa  mov     [rbp+ImpersonationLevel], 0
0x140069c01  lea     rdx, [rbp+CopyOnOpen]; CopyOnOpen
0x140069c05  mov     [rbp+TokenInformation], 0
0x140069c0d  mov     rcx, gs:188h; Thread
0x140069c16  call    cs:__imp_PsReferenceImpersonationToken
0x140069c1d  nop     dword ptr [rax+rax+00h]
0x140069c22  mov     rsi, rax
0x140069c25  test    rax, rax
0x140069c28  jz      short loc_140069BD7
0x140069c2a  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140069c2e  mov     edx, 21h ; '!'; TokenInformationClass
0x140069c33  mov     rcx, rax; Token
0x140069c36  call    cs:__imp_SeQueryInformationToken
0x140069c3d  nop     dword ptr [rax+rax+00h]
0x140069c42  mov     r9d, eax
0x140069c45  test    eax, eax
0x140069c47  js      loc_140069D1F
0x140069c4d  mov     rcx, [rbp+TokenInformation]; P
0x140069c51  mov     ebx, [rcx+4]
0x140069c54  test    ebx, ebx
0x140069c56  setz    r14b
0x140069c5a  xor     edx, edx; Tag
0x140069c5c  call    cs:__imp_ExFreePoolWithTag
0x140069c63  nop     dword ptr [rax+rax+00h]
0x140069c68  mov     [rbp+TokenInformation], 0
0x140069c70  test    ebx, ebx
0x140069c72  jnz     short loc_140069CB6
0x140069c74  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140069c78  mov     rcx, rsi; Token
0x140069c7b  lea     edx, [rbx+22h]; TokenInformationClass
0x140069c7e  call    cs:__imp_SeQueryInformationToken
0x140069c85  nop     dword ptr [rax+rax+00h]
0x140069c8a  test    eax, eax
0x140069c8c  js      short loc_140069CB6
0x140069c8e  mov     rcx, [rbp+TokenInformation]; P
0x140069c92  xor     edi, edi
0x140069c94  movzx   eax, r14b
0x140069c98  cmp     [rcx+4], edi
0x140069c9b  cmovbe  edi, eax
0x140069c9e  xor     edx, edx; Tag
0x140069ca0  call    cs:__imp_ExFreePoolWithTag
0x140069ca7  nop     dword ptr [rax+rax+00h]
0x140069cac  mov     [rbp+TokenInformation], 0
0x140069cb4  jmp     short loc_140069CB9
0x140069cb6  mov     dil, r14b
0x140069cb9  test    dil, dil
0x140069cbc  jz      loc_140069D59
0x140069cc2  lea     r8, [rbp+P]; TokenInformation
0x140069cc6  mov     [rbp+P], 0
0x140069cce  mov     edx, 25h ; '%'; TokenInformationClass
0x140069cd3  mov     rcx, rsi; Token
0x140069cd6  call    cs:__imp_SeQueryInformationToken
0x140069cdd  nop     dword ptr [rax+rax+00h]
0x140069ce2  test    eax, eax
0x140069ce4  js      short loc_140069D0A
0x140069ce6  mov     rcx, [rbp+P]; P
0x140069cea  xor     ebx, ebx
0x140069cec  movzx   eax, dil
0x140069cf0  cmp     [rcx], ebx
0x140069cf2  cmovbe  ebx, eax
0x140069cf5  xor     edx, edx; Tag
0x140069cf7  call    cs:__imp_ExFreePoolWithTag
0x140069cfe  nop     dword ptr [rax+rax+00h]
0x140069d03  mov     dil, bl
0x140069d06  test    bl, bl
0x140069d08  jz      short loc_140069D59
0x140069d0a  call    cs:__imp_SrvLibHasClaimsSentinel
0x140069d11  nop     dword ptr [rax+rax+00h]
0x140069d16  test    al, al
0x140069d18  jz      short loc_140069D59
0x140069d1a  xor     dil, dil
0x140069d1d  jmp     short loc_140069D59
0x140069d1f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140069d26  lea     rax, WPP_GLOBAL_Control
0x140069d2d  mov     dil, 1
0x140069d30  cmp     rcx, rax
0x140069d33  jz      short loc_140069D59
0x140069d35  test    dword ptr [rcx+2Ch], 20000h
0x140069d3c  jz      short loc_140069D59
0x140069d3e  cmp     [rcx+29h], dil
0x140069d42  jb      short loc_140069D59
0x140069d44  mov     rcx, [rcx+18h]
0x140069d48  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x140069d4f  mov     edx, 32h ; '2'
0x140069d54  call    WPP_SF_d
0x140069d59  mov     rcx, rsi; ImpersonationToken
0x140069d5c  call    cs:__imp_PsDereferenceImpersonationToken
0x140069d63  nop     dword ptr [rax+rax+00h]
0x140069d68  call    Smb2Revert
0x140069d6d  mov     al, dil
0x140069d70  jmp     loc_140069BDE
```
